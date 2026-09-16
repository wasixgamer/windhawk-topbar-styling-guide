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
* [Style syntax](#style-syntax)
  * [Target syntax](#target-syntax)
  * [Value syntax](#value-syntax)
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
* [Weather](#weather)
* [Recycle bin](#recycle-bin)
* [Resource monitor](#resource-monitor)
* [Colors](#colors)

## Themes

Themes are collections of styles that can be selected from the **Theme** dropdown in the mod settings. Following is the list of themes available:

| Link | Screenshot |
| ----- | ---------- |
| [GreenBar](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/GreenBar) | [![GreenBar](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/GreenBar/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/GreenBar) |
| [NoIslands](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/NoIslands) | [![NoIslands](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/NoIslands/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/NoIslands) |
| [OS27 GoldenGate](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/OS27%20GoldenGate) | [![OS27 GoldenGate](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/OS27%20GoldenGate/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/OS27%20GoldenGate) |

More themes can be contributed to the mod. Contributions are welcome.

## Introduction

The TopBar mod adds a second, fully independent taskbar docked to the top of the screen. It features:

- **Task list** — window icons, titles, click-to-activate, double-click maximize.
- **Control centre** — Display (brightness, Dark Mode), Sound (volume, per-app mixer, device picker, media controls), Wi-Fi (scan/connect), Bluetooth (connect/disconnect), Battery, Weather, Recycle Bin, and Resource Monitor (CPU/RAM/GPU).
- **Full styling** via Control styles.
- **Background translucency** tinting for the TopBar, and WindhawkBlur for flyouts and context menus.

### Supported components

- Top taskbar
- Flyout panels (Display, Sound, Wi-Fi, Bluetooth, Battery, Weather, Recycle Bin, Resource Monitor, Settings)
- Context menus (Start, Task buttons, Tray items)
- All flyouts and menus including submenus

### Finding targets

Run **[UWPSpy](https://github.com/m417z/UWPSpy/releases/)** against the TopBar's
`explorer.exe` process (the one started with `-tool-mod windhawk-topbar`), or
press **Ctrl+D** while hovering any TopBar element to show a small tooltip with
the element's `ClassName#Name`. Ctrl+D works on the top bar and inside any open
flyout or menu.

See also: [How to find targets using UWPSpy](https://github.com/bbmaster123/FWFU/blob/main/Guides/uwpspy.md).

## Style syntax

Every rule lives in **Control styles** and consists of a `Target` and one or
more `Styles` entries.

### Target syntax

| Syntax | Matches |
|--------|---------|
| `Button` | any `Button` by class name |
| `Button#StartButton` | a `Button` whose `Name` is `StartButton` |
| `StartButton` | a `Name`, or a class if no element by that name matches |
| `StackPanel > TextBlock` | a `TextBlock` whose direct parent is a `StackPanel` |
| `Grid > * > TextBlock` | a `TextBlock` with any chain of ancestors in between |
| `:root > Grid` | a root `Grid` with no parent FrameworkElement |
| `Button[3]` | the 3rd child of its parent |
| `Button[Width=200]` | a `Button` whose local `Width` is `200` |
| `Button@CommonStates` | an element exposing the `CommonStates` VisualStateGroup |
| `StartButton, SearchButton` | multiple targets separated by commas |

Comma-separated targets in a single rule are equivalent to writing one rule per
target with the same styles.

### Value syntax

| Syntax | Meaning |
|--------|---------|
| `Prop=Value` | set a property with a parsed value |
| `Prop:=<Xaml/>` | set a property with an inline XAML fragment |
| `$name` | substitute a value from **Style constants** |
| `Prop@VisualState=Value` | only apply while the element is in that VisualState |
| `Prop=>VarName` | capture the element's current `Prop` into `VarName` |
| `{{VarName}}` | substitute a captured variable |
| `{{W - 12}}` | arithmetic on captured variables (`+ - * /`, `min`, `max`, `?:`) |

Captured variables are per-XamlRoot and are evaluated in the visual tree, so a
consumer reads the value of the closest capturer above it in the tree. This is
useful for deriving sizes from live layout — for example capturing a
`TaskButton`'s `ActualWidth` and using it to size something else.

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

### Bar margin

Target:

    TopBarRoot

Style:

    Margin=<left>,<top>,<right>,<bottom>

Useful for floating the bar off the screen edge (e.g. `Margin=6,4,6,0`), and for
revealing the corner radius all the way around.

### Bar border

Target:

    TopBarRoot

Style:

    BorderBrush:=<color>
    BorderThickness=<number>

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
    CornerRadius=<radius>
    Margin=<left>,<top>,<right>,<bottom>

### Task icon size

Target:

    TaskButtonIcon

Style:

    Width=<size>
    Height=<size>

### Task button text

Target:

    TaskButtonText

Style:

    Foreground=<color>
    FontSize=<size>

## Control center

### Status buttons

Targets:

    DisplayButton
    SoundButton
    WifiButton
    BluetoothButton
    BatteryButton
    WeatherButton
    RecycleBinButton
    ResourceButton
    SettingsButton

Style:

    Background:=<color>
    BorderBrush:=<color>
    BorderThickness=<number>
    CornerRadius=<radius>

### Flyout panels

The flyout panel roots are:

    DisplayFlyoutRoot
    SoundFlyoutRoot
    WifiFlyoutRoot
    BluetoothFlyoutRoot
    BatteryFlyoutRoot
    WeatherFlyoutRoot
    RecycleBinFlyoutRoot
    ResourceFlyoutRoot

Flyout shells (the presenter border behind every flyout) can be styled with:

    Canvas > FlyoutPresenter > Grid > Border#PART_BackgroundBorder

And context menu shells with:

    Canvas > MenuFlyoutPresenter > Grid > Border#PART_BackgroundBorder

A rule targeting `Border#PART_BackgroundBorder` on its own hits every flyout
and menu shell at once.

### Toggle switches

Toggle switches appear in the Wi-Fi and Bluetooth panel headers.

Targets:

    WifiHeaderToggle
    BluetoothHeaderToggle

Style:

    Width=<size>
    MinWidth=<size>

## System tray

### Tray panel

Target:

    TrayPanel

Style:

    Background:=<color>
    CornerRadius=<radius>
    Margin=<left>,<top>,<right>,<bottom>

### Tray items

Individual tray buttons are named after the button they wrap:

    ClockButton / ClockText
    BatteryButton
    WeatherButton / WeatherButtonText / WeatherIcon
    RecycleBinButton / RecycleBinIcon
    ResourceButton

## Weather

Targets in the weather button and its flyout:

    WeatherButton / WeatherButtonText
    WeatherIcon
    WeatherLocationBox
    WeatherSetLocationButton
    WeatherCurrentTemp
    WeatherDesc

## Recycle bin

Targets in the recycle bin button and its flyout:

    RecycleBinButton / RecycleBinIcon
    RecycleBinSizeText
    RecycleBinCountText
    RecycleBinEmptyButton

## Resource monitor

Targets in the resource button and its flyout:

    ResourceButton
    ResourceFlyoutRoot

## Colors

### Solid color

Use a color name (e.g. `Red`) or a hex code (e.g. `#FF0000`). Semi-transparent colors are supported (e.g. `#80FF0000`). Use `Transparent` for fully transparent.

### WindhawkBlur effect

For a blurred background, use the mod's built-in `WindhawkBlur` brush:

    Background:=<WindhawkBlur BlurAmount="10" TintColor="#80ff0000" />

- `BlurAmount`: Radius of blur.
- `TintColor`: Hex color (`#AARRGGBB` or `#RRGGBB`).
- `TintOpacity`: Overrides the alpha of `TintColor`.

`TintColor` and `TintOpacity` are both optional. Leaving both off gives a plain
blur with no tint overlay:

    Background:=<WindhawkBlur BlurAmount="18" />

WindhawkBlur can be used on any brush-typed property, not just `Background`:
`Fill`, `BorderBrush`, `Stroke`, and so on. It works on the top bar, all
flyouts, and all context menus and submenus.

### Gradient

Use XAML gradient brushes:

    Background:=<LinearGradientBrush StartPoint="0,0.5" EndPoint="1,0.5"><GradientStop Color="Yellow" Offset="0.0" /><GradientStop Color="Red" Offset="0.25" /><GradientStop Color="Blue" Offset="0.75" /><GradientStop Color="LimeGreen" Offset="1.0" /></LinearGradientBrush>

### Image

Use an image as background:

    Background:=<ImageBrush Stretch="UniformToFill" ImageSource="<image>" />

Replace `<image>` with a URL or local file path.

---

## Work in progress

*This document is a work in progress, contributions are welcome.*
