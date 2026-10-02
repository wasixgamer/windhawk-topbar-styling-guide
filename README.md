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
  * [Style constants](#style-constants)
* [General](#general)
  * [Bar Stylings](#bar-stylings)
* [Task list](#task-list)
  * [Task button Stylings](#task-button-stylings)
* [Control center](#control-center)
  * [Status buttons](#status-buttons)
  * [Flyout panels](#flyout-panels)
  * [Toggle switches](#toggle-switches)
* [Start menu](#start-menu)
* [Search](#search)
* [Media Player](#media-player)
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
| [Midnight Neon](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/Midnight%20Neon) | [![Midnight Neon](https://github.com/wasixgamer/windhawk-topbar-styling-guide/raw/main/Themes/Midnight%20Neon/screenshot.png)](https://github.com/wasixgamer/windhawk-topbar-styling-guide/tree/main/Themes/Midnight%20Neon) |

More themes can be contributed to the mod. Contributions are welcome.

## Introduction

The TopBar mod adds a second, fully independent taskbar docked to the top of the screen. It features:

- **Task list** — window icons, titles, click-to-activate, double-click maximize, per-window right-click menu. Can be swapped for a single **Application name** button showing the current foreground app.
- **Control centre** — Display (brightness, per-monitor sliders, Dark Mode, Night light), Sound (volume, per-app mixer, output device picker, mute), Wi-Fi (scan / connect / disconnect / password entry), Bluetooth (scan, pair, connect, battery level), Battery (percentage, health), Weather (current conditions, hourly forecast, location search), Recycle Bin (size, item count, empty with confirm), Resource Monitor (CPU / RAM / GPU tabs with live graph, GPU selector), and Media Player (album art, transport controls, live progress bar, audio-reactive visualizer).
- **Start menu replacement** — custom Start with account panel, power menu, search box and a 5-column all-apps grid (Win32 shortcuts + UWP apps). Optional: make it the default for Win key and taskbar Start.
- **Search replacement** — Spotlight-style search across apps, files, Windows Settings pages and Control Panel items. Optional: make it the default for Win+S / Win+Q and the taskbar search box.
- **Full styling** via Control styles.
- **Background translucency** tinting for the TopBar, and WindhawkBlur for flyouts and context menus.
- **Import / Export** — save or restore the entire configuration as JSON.

### Supported components

- Top taskbar (root, panels, every button)
- Flyout panels (Display, Sound, Wi-Fi, Bluetooth, Battery, Weather, Recycle Bin, Resource Monitor, Control Center, Media Player)
- Start menu and Search flyouts
- Context menus (Start, Task buttons, Tray items, Search results, Start tiles)
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

### Style constants

Style constants let you name a value once and reuse it across many rules. Define
them under **Style constants** as `name=value` pairs, then reference them with
`$name` anywhere in a style value:

```yaml
styleConstants:
  - 'NeonAccent=#8FD9F0'
  - 'NeonCard=#16243A'
  - 'GlassBlur=<WindhawkBlur BlurAmount="16" TintColor="#0E1B33" TintOpacity="0.65" />'

controlStyles:
  - target: SettingsButton
    styles:
      - 'Background:=$NeonCard'
      - 'IconColor=$NeonAccent'

  - target: FlyoutBlurHost
    styles:
      - 'Background:=$GlassBlur'
```

Constants work in every value position, including inside `<WindhawkBlur …>`,
gradients, and XAML fragments. The OS27 GoldenGate theme uses two constants
(`$GoldenGateBackground`, `$GoldenGateBorder`) so a single edit retunes the
whole look.

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

### Panels

The bar is split into four sections. Each is a `StackPanel` and can be styled
directly:

    LeftPanel
    CenterPanel
    TrayPanel
    ClockPanel

`TaskListPanel` is a sibling panel — the middle section holds either the task
list or the application-name button depending on the **App title button mode**
setting.

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

### Application name button

When **App title button mode** is set to `applicationButtons`, the middle section
shows a single button with the current foreground application's name:

    AppTitleButton
    AppTitleText

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
    ControlCenterButton
    MediaButton

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
    MediaFlyoutRoot
    ControlCenterFlyoutRoot

Flyout shells (the presenter border behind every flyout) can be styled with:

    Canvas > FlyoutPresenter > Grid > Border#PART_BackgroundBorder

And context menu shells with:

    Canvas > MenuFlyoutPresenter > Grid > Border#PART_BackgroundBorder

A rule targeting `Border#PART_BackgroundBorder` on its own hits every flyout
and menu shell at once.

### Common flyout elements

Every control flyout shares these named elements:

    FlyoutBlurHost      — the blur host border behind the whole flyout
    FlyoutTitle         — the panel's title TextBlock
    FlyoutDivider       — 1px separators between sections
    FlyoutListRow       — clickable list rows (Wi-Fi networks, devices, …)
    FlyoutFooterLink    — "open the real Settings page" footer links

### Toggle switches

Toggle switches appear in the Wi-Fi and Bluetooth panel headers.

Targets:

    WifiHeaderToggle
    BluetoothHeaderToggle

Style:

    Width=<size>
    MinWidth=<size>

### Wi-Fi panel

    WifiHeaderGrid / WifiHeaderLeftStack / WifiHeaderRightStack
    WifiProgressRing
    WifiRefreshButton
    WifiNetworkRow
    WifiIcon
    WifiPasswordBox
    WifiConnectButton / WifiCancelButton

### Bluetooth panel

    BluetoothHeaderGrid / BluetoothHeaderLeftStack / BluetoothHeaderRightStack
    BluetoothProgressRing
    BluetoothRefreshButton
    BluetoothDeviceRow

### Media Player flyout

    MediaProgressBar
    MediaPositionText
    MediaEndText

The transport buttons inside the flyout are named `MediaTransportButton`; the
ones embedded in the topbar's Media button also use that name.

## Start menu

The TopBar Start menu is a XAML flyout with several named elements:

    StartMenuSearchBox        — the search box at the top
    StartMenuPowerButton      — power glyph button (right of the search box)
    StartMenuAccountButton    — avatar / account button (left of the search box)

App tiles in the grid use the shared `TaskButton`-like look but aren't
individually named. Style them via the ancestor chain, e.g.:

    Grid > Button

## Search

The Spotlight-style Search flyout:

    SearchBlurHost            — the blur host border behind the whole flyout
    SpotlightSearchBox        — the main search input
    SearchAnchor              — hidden anchor Grid used for placement (do not style)
    SearchResultRow           — individual result rows

## Media Player

Targets in the media button and its flyout:

    MediaButton
    MediaTransportButton      — previous / play-pause / next
    MediaProgressBar          — live progress bar in the flyout
    MediaPositionText         — current time (left of the bar)
    MediaEndText              — total length (right of the bar)

## Weather

Targets in the weather button and its flyout:

    WeatherButton / WeatherButtonContent
    WeatherIcon
    WeatherSearchBox
    WeatherSearchResults
    WeatherCityRow
    WeatherPickerCancel
    WeatherScrollLeft / WeatherScrollRight
    WeatherChangeLocation
    WeatherCityName
    WeatherCurrentTemp
    WeatherDesc
    WeatherMinMax

## Recycle bin

Targets in the recycle bin button and its flyout:

    RecycleBinButton / RecycleBinIcon
    RecycleBinSizeText
    RecycleBinCountText
    RecycleBinEmptyButton
    RecycleBinConfirmButton
    RecycleBinCancelButton
    RecycleBinWarning

## Resource monitor

Targets in the resource button and its flyout:

    ResourceButton
    ResourceFlyoutRoot
    ResourceTabPanel
    ResourceCpuTab / ResourceCpuTabIcon / ResourceCpuTabText
    ResourceRamTab / ResourceRamTabIcon / ResourceRamTabText
    ResourceGpuTab / ResourceGpuTabIcon / ResourceGpuTabText
    ResourceGraphBorder
    ResourceGraphCanvas
    ResourceContentGrid
    ResourceStatsGrid
    InfoIsland                — the component-info card above the graph
    InfoCpuLabel / InfoCpuName
    InfoRamLabel / InfoRamName
    InfoGpuLabel
    GpuSelector               — the GPU ComboBox
    StatLabel0..3 / StatValue0..3

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