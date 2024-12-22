---
title: Luanti on mobile devices
bookCollapseSection: true
aliases:
- /Luanti_on_Android
---

# Luanti on mobile devices

Luanti supports mobile devices and can be played using a touchscreen.

If you're developing a game or mod, you can follow [this advice](/mobile/improving-games-and-mods-for-mobile) to make it more usable on mobile.

## Android

There is an official Android version. It's available on the [Luanti website](https://www.luanti.org/downloads/), on [Google Play](https://play.google.com/store/apps/details?id=net.minetest.minetest) and on [F-Droid](https://f-droid.org/packages/net.minetest.minetest/).

Traditionally, the Android version only supported the touchscreen controls. Starting with version 5.10.0[^1], the desktop controls also work out of the box if you connect mouse and keyboard via bluetooth, without any special configuration required.

Useful resources:

- [Accessing Android Data Directory](/mobile-support/accessing-android-data-directory)

Please do not download unofficial Luanti builds from the Google Play and any other app store. The builds found there may contain excessive adverts or spyware. They may be distributed under proprietary terms, without the source code, which makes them illegal to develop. They may be old or unsupported.

## Linux phones

You can also play Luanti on Linux phones. Starting with version 5.9.0[^2], Luanti should work on Linux phones out of the box, without any special configuration required. However, Luanti may work better on Linux phones if you compile it yourself with `-DUSE_SDL2=TRUE`. All official release builds have been compiled with `-DUSE_SDL2=FALSE` so far.

## iOS

There is no iOS support due to legal uncertainties and lack of developer time. While the "MultiCraft" fork of Luanti supports iOS, it contains advertising and is still based on the outdated engine version 5.4.1, so it isn't recommended.

[^1]: See PR [#14542](https://github.com/minetest/minetest/pull/14542) and its various predecessors.
[^2]: See PRs [#14075](https://github.com/minetest/minetest/pull/14075) and [#14400](https://github.com/minetest/minetest/pull/14400).
