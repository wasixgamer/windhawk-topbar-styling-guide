# The Windhawk TopBar Styling Guide

## Support the Creator

If you enjoy this mod and want to support its development, consider becoming a patron:

[![Patreon](https://img.shields.io/badge/Support%20on-Patreon-orange)](https://www.patreon.com/WasiXGamer/join)

Your support helps me continue improving the TopBar and adding new features. Thank you!


This guide provides a collection of styling customizations for the **TopBar for Windhawk** mod, a feature-rich top taskbar hosted by a dedicated Explorer tool process.

If you're not familiar with Windhawk, here are the steps for installing the mod:

- Download Windhawk from [windhawk.net](https://windhawk.net/) and install it.
- Go to "Mods" in the upper right menu.
- Find and install the **TopBar for Windhawk** mod.

After installing the mod, open its Settings tab and adjust the styles according to your preferences.

## Table of contents

* [Themes](#themes)
* [Introduction](#introduction)
  * [Supported components](#supported-components)
  * [Finding targets](#finding-targets)
* [General](#general)
  * [Bar Stylings](#bar-stylings)
* [Task list](#task-list)
  * [Task button Stylings](#task-button-stylings)
* [Control center](#control-center)
  * [Status buttons](#status-buttons)
  * [Flyout panels](#flyout-panels)
  * [Toggle switches](#toggle-switches)
* [System tray](#system-tray)
  * [Tray panel](#tray-panel)
  * [Tray items](#tray-items)
* [Colors](#colors)



## Themes

Themes are collections of styles that can be selected from the **Theme** dropdown in the mod settings. Following is the list of themes available:

| Link | Screenshot |
| ----- | ---------- |
| [GreenBar](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/GreenBar) | [![GreenBar](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/GreenBar/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/GreenBar) |
| [NoIslands](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/NoIslands) | [![NoIslands](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/NoIslands/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/NoIslands) |

More themes can be contributed to the mod. Contributions are welcome.


## Introduction

The TopBar mod adds a second, fully independent taskbar docked to the top of the screen. It features:

- **Task list** — window icons, titles, click-to-activate, double-click maximize.
- **Control centre** — Display (brightness, Night Light, Dark Mode), Sound (volume, per-app mixer, device picker, media controls), Wi-Fi (scan/connect), Bluetooth (connect/disconnect), and Tray (notification area).
- **Full styling** via Control styles.
- **Background translucency** with acrylic/blur.

### Supported components

- Top taskbar
- Flyout panels (Display, Sound, Wi-Fi, Bluetooth, Tray)
- Context menus (Start, Task buttons)

### Finding targets

Targets can be found using **UWPSpy** by attaching to the top bar process (`explorer.exe -tool-mod windhawk-topbar`). See [How to find targets using UWPSpy](https://github.com/bbmaster123/FWFU/blob/main/Guides/uwpspy.md).

## General

### Bar height

Use the **Bar height (DIP)** setting in the mod settings. The default is `40`.

### Bar background

Target:

    TopBarRoot

Style:

    Background:=<color>

For a blurred/translucent background, use a `WindhawkBlur` brush (see [Colors](#colors)).

### Bar corner radius

Target:

    TopBarRoot

Style:

    CornerRadius=<radius>

## Task list

### Task button content

The task button can show icons, text, or both. This is controlled by the **Task button content** setting. Options: `iconAndText`, `iconOnly`, `textOnly`.

### Task button Stylings

Target:

    TaskButton

Style:

    Background:=<color>
    BorderBrush:=<color>
    BorderThickness=<number>

### Task icon size

Target:

    TaskButtonIcon

Style:

    Width=<size>
    Height=<size>


## Control center

### Status buttons

Targets:

    DisplayButton
    SoundButton
    WifiButton
    BluetoothButton
    TrayButton

Style:

    Background:=<color>
    BorderBrush:=<color>
    BorderThickness=<number>

### Flyout panels

The flyout panel roots are:

    DisplayFlyoutRoot
    SoundFlyoutRoot
    WifiFlyoutRoot
    BluetoothFlyoutRoot
    TrayFlyoutRoot

You can style the panel background, title, etc.
## Colors

### Solid color

Use a color name (e.g. `Red`) or a hex code (e.g. `#FF0000`). Semi-transparent colors are supported (e.g. `#80FF0000`). Use `Transparent` for fully transparent.

### WindhawkBlur effect
> [!NOTE]
> The Windhawk Blur is not working currently. It will be Fixed Later.

For a blurred background, use the mod's built-in `WindhawkBlur` brush:

    Background:=<WindhawkBlur BlurAmount="10" TintColor="#80ff0000" />

- `BlurAmount`: Radius of blur (default 10).
- `TintColor`: Hex color (`#AARRGGBB` or `#RRGGBB`).
- `TintOpacity`: Overrides the alpha of `TintColor`.

### Gradient

Use XAML gradient brushes:

    Background:=<LinearGradientBrush StartPoint="0,0.5" EndPoint="1,0.5"><GradientStop Color="Yellow" Offset="0.0" /><GradientStop Color="Red" Offset="0.25" /><GradientStop Color="Blue" Offset="0.75" /><GradientStop Color="LimeGreen" Offset="1.0" /></LinearGradientBrush>

### Image

Use an image as background:

    Background:=<ImageBrush Stretch="UniformToFill" ImageSource="<image>" />

Replace `<image>` with a URL or local file path.

---

This guide covers the most common customizations. For more advanced styling, refer to the mod's **Control styles** and **Style constants** settings. Contributions and theme submissions are welcome via pull requests to [this repository](https://github.com/wasixgamer/windhawk-topbar-styling-guide).
