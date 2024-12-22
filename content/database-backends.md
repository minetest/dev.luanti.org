---
title: Database backends
aliases:
- /Database_backends
---

# Database backends

Luanti supports several database backends. This page provides a comparison of all backends.

There are four database backends in Luanti (since 5.6.0):

-   Map
-   Players
-   Authentication
-   Mod Storage

## Map backend

The database backend is set using the `backend` setting in *world.mt*. Put the name of the backend in lowercase as the value of the setting (e.g. `backend=sqlite3` for SQLite3).

If you want to migrate a world map to a new backend, use `minetestserver --migrate <name of new backend> --world <path to your world directory>`. It will automatically update world.mt to reflect the new backend.

If using a client build, server instructions can be given using `minetest --server`, e.g. `minetest --server --migrate <name of new backend> --world <path to your world directory>`.

## Player backend

The database backend is set using the `player_backend` setting in *world.mt*. If it doesn't exist, the default is *files*.

If you want to migrate players to a new backend, use `minetestserver --migrate-players <name of new backend> --world <path to your world directory>`. It will automatically update world.mt to reflect the new backend.

## Authentication backend

The database backend is set using the `auth_backend` setting in *world.mt*. If it doesn't exist, the default is *files*.

If you want to migrate the authentication data to a new backend, use `minetestserver --migrate-auth <name of new backend> --world <path to your world directory>`. It will automatically update world.mt to reflect the new backend.

## Mod Storage backend

The database backend is set using the `mod_storage_backend` setting in *world.mt*. If it doesn't exist, the default is *files*.

If you want to migrate mod storage to a new backend, use `minetestserver --migrate-mod-storage <name of new backend> --world <path to your world directory>`. It will automatically update world.mt to reflect the new backend.

## Comparison table

This table is a rough estimate of what you may expect from each database backend in terms of speed, reliability and compatibility. It is elaborated on in each section, and your mileage may vary.

| Backend            | Speed                                                            | Reliability   | Compatibility with builds                       | Map | Players | Authentication | Mod Storage                                                                        |
| ------------------ | ---------------------------------------------------------------- | ------------- | ----------------------------------------------- | --- | ------- | -------------- | ---------------------------------------------------------------------------------- |
| SQLite3            | **Good**                                                         | **Good**      | **Very good** _(always supported)_              | ✔   | ✔       | ✔              | ✔ (5.5.0+)                                                                         |
| LevelDB            | **Good**                                                         | **Bad**       | **Mostly supported**                            | ✔   | ✔       | ✔              |                                                                                    |
| Redis              | **Very good** _(data kept in RAM)_                               | **Good**      | **Inconvenient** _(Redis server required)_      | ✔   |         |                |                                                                                    |
| PostgreSQL         | **Very good** _(most used data are in memory, others from disk)_ | **Very good** | **Inconvenient** _(PostgreSQL server required)_ | ✔   | ✔       | ✔              | ✔ (5.7.0+) _([very slow](https://niklp.net/posts/minetest-postgresql-benchmark/))_ |
| Dummy              | **N/A**                                                          | **N/A**       | **N/A**                                         | ✔   | ✔       |                |                                                                                    |
| Files (deprecated) | **Bad**                                                          | **Bad**       | **Deprecated** _(support may be removed)_       |     | ✔       | ✔              | ✔                                                                                  |

The *Compatibility with builds* column is only relevant if you want to distribute the worlds.

### SQLite3

SQLite3 is the default backend for all Luanti backends, it is supported by every Luanti build and is therefore the standard database format that is used to distribute worlds.

It has decent speeds, good reliability and works out of the box without configuration making it perfect for singleplayer worlds and small servers.

### LevelDB

LevelDB offers better speeds and also compression for smaller filesizes compared to SQLite, but LevelDB as a database suffers from serious reliability issues that are well known both inside and outside of Luanti [^1][^2][^3][^4][^5][^6][^7][^8]. Random corruption may occur including to but not limited to during powerloss or any other unexpected shutdown where the database is not safely closed. It should be used with caution.

LevelDB support is included in the official Windows builds and most Linux builds.

### Redis

Redis support for the map backend was added to Luanti in April 2014, Redis is mainly useful for servers as it allows multiple worlds to be stored in one Redis instance. You need to install it additionally (*libhiredis* library) and Luanti needs to compiled with support for it.

Information about setting up a Redis server can be found here: <https://redis.io/topics/quickstart>

#### world.mt settings for Redis

-   `redis_address`: The IP or hostname of the redis server.
-   `redis_port`: The port of the redis server. *Optional, default: 6379*
-   `redis_hash`: Hash where the MapBlocks are stored in, if you want multiple worlds in one redis instance this needs to be different for each world. If you don't need that you can use e.g. `IGNORED`.

### PostgreSQL

PostgreSQL support was added to Luanti in May 2016, it's mainly useful for servers as it allows multiple worlds in a single instance, in multiple databases.

PostgreSQL is an excellent alternative to Redis. It doesn't store all data in memory, only recent and frequent data is loaded into memory. All data is on disk storage and data storage is very robust. You can also easily interface a website in front of your database to offer a frontend to your users.

While we support older versions, it is recommended to use PostgreSQL 9.5 at least for UPSERT functionality.

To improve PostgreSQL's performance with Luanti servers, please configure `postgresql.conf` with a minimum `shared_buffer` of 512MB, with a maximum of 50% of your server's available RAM.

#### world.mt for PostgreSQL

-   `pgsql_connection`: PostgreSQL connection string for world map \| `host=<db_host> user=<db_user> password=<db_password> dbname=<db_name>`
-   `pgsql_player_connection`: PostgreSQL connection string for players \| `host=<db_host> user=<db_user> password=<db_password> dbname=<db_name>`
-   `pgsql_auth_connection`: PostgreSQL connection string for auth \| `host=<db_host> user=<db_user> password=<db_password> dbname=<db_name>`
-   `pgsql_mod_storage_connection`: PostgreSQL connection string for mod storage \| `host=<db_host> user=<db_user> password=<db_password> dbname=<db_name>`

### MariaDB

MariaDB support is currently pending [(see PR #13266)](https://github.com/minetest/minetest/pull/13266). It allows about the same capabilities as PostgreSQL.

To use the MariaDB database backend, the MariaDB C++ connector is required which usually is not part of the MariaDB package. You can find the [source code for it here](https://github.com/mariadb-corporation/mariadb-connector-cpp).

### Dummy

A dummy database backend, which stores all MapBlocks in RAM without saving them. This means, as soon the server shuts down or you leave in singleplayer, all changes made to the world are lost. When you re-join, the world will be re-generated from scratch.

This backend is used by servers which don't need a persistent map, such as Capture the Flag. It can also be useful for development when testing map generation capabilities.

### Files

A legacy backend for player and authentification data. Everything is stored in plaintext files. It's slow, unreliable and clunky. Use of this backend is discouraged now and it's possible this backend will be removed in the future.

For mod storage, Files uses the legacy JSON-based storage method as opposed to a regular database system. It is slower and will keep the entire mod storage data in memory.

## References

[^1]: [Avoiding LevelDB in Minetest for now](https://lazyjminetest.blogspot.com/2014/09/avoiding-leveldb-in-minetest-for-now.html)

[^2]: [Issues · google/leveldb · GitHub](https://github.com/google/leveldb/issues?utf8=%E2%9C%93&q=corrupt+is%3Aissue)

[^3]: [Unrecoverable corruption in Chromium](https://bugs.chromium.org/p/chromium/issues/detail?id=261623)

[^4]: [Corruption in syncthing](https://forum.syncthing.net/t/panic-leveldb-table-corruption-on-data-block/2526/23)

[^5]: [Corruption after power loss](https://github.com/google/leveldb/issues/333)

[^6]: [Corruption in Ethereum](http://ethereum.stackexchange.com/questions/1159/corruption-on-data-block-while-synchronising)

[^7]: [LevelDB reliability?](https://bitcointalk.org/index.php?topic=1394020.0)

[^8]: [Does LevelDB still corrupt data?](https://stackoverflow.com/questions/40675204/does-leveldb-still-corrupt-data)
