---
title: Improving games and mods for mobile
---

# Improving games and mods for mobile

The mobile platform is different from the desktop platform. You can't develop a Luanti game for desktop and expect it to work on mobile without any adjustments. While Luanti needs to improve support for mobile by adding more mobile-specific features to the Lua API, that's not enough for mobile players to have a good experience. In the end, it will always be up to games and mods to use these APIs.

All games and mods uploaded to ContentDB are available on Android and all servers can be joined on Android, so you will have some mobile players either way.

If you want to improve mobile support in your game or mod, the most important thing to do is testing it on mobile. Play for some time, try doing different things and see what works and what doesn't. This page lists some common problems and offers solutions.

## Touch controls: It's impossible to hold the place button / right mouse button

In the touch controls, a long tap corresponds to pressing and holding the dig button and a short tap corresponds to briefly pressing the place button.

This works well when only digging and placing nodes, but not in other scenarios. Some actions require the player to hold the place button, for example shooting with a bow or eating food in Minecraft-like games. Some actions require the player to be able to press the dig button very quickly, for example throwing grenades in [Capture the Flag](https://content.luanti.org/packages/rubenwardy/capturetheflag/).

Luckily, it's possible to customize the meaning of long and short taps using the `touch_interaction` field in item definitions. As a solution for the cases described above, you can add the following line to your item definition:

```lua
touch_interaction = "short_dig_long_place",
```

This feature is available since engine version 5.9.0, older versions ignore it.

## Android: Formspec text fields without a separate submit button cannot be submitted

On desktop, you can submit text fields in formspecs by pressing the `Enter` key, so you don't necessarily need a separate submit button.

On Android, tapping a text field will open a text input dialog with the screen keyboard. When the user taps `Enter`, it's not possible for Luanti to distinguish whether the user actually wants to press `Enter` or whether they just want to close the dialog. By default, tapping `Enter` only closes the text input dialog without emitting an `Enter` keypress. This means it's not possible for Android users to submit text fields without a submit button.

![](/images/improving-games-and-mods-for-mobile/android-text-input-dialog.jpeg)  
_The Android text input dialog_

Available solutions:

- Use the `field_enter_after_edit[]` formspec element on the text field

  If this is set to true for a specific text field, an `Enter` keypress will be emitted after closing the text input dialog. This is used by e.g. the server list search field on the "Join Game" tab of the main menu.

  This formspec element is available since engine version 5.8.0, older versions ignore it.

- Add a submit button next to the text field

  This also works, but is worse than `field_enter_after_edit[]` as the user needs to do two taps instead of one. It may also still be confusing for the user ("I already pressed `Enter`, why didn't anything happen?"). Ideally, you would add both `field_enter_after_edit[]` and a submit button.
