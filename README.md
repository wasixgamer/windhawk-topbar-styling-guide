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
  * [Control Center Tiles](#control-center-tiles)
  * [Flyout panels](#flyout-panels)
  * [Toggle switches](#toggle-switches)
* [Start menu](#start-menu)
* [Search](#search)
* [Media Player](#media-player)
* [Weather](#weather)
* [Recycle bin](#recycle-bin)
* [Resource monitor](#resource-monitor)
* [System Tray](#system-tray)
* [Notifications](#notifications)
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
- **System Tray & Notifications** — Native tray icon overflow replacement and notification center integration.
- **Full styling** via Control styles.
- **Background translucency** tinting for the TopBar, and WindhawkBlur for flyouts and context menus.
- **Import / Export** — save or restore the entire configuration as JSON.

### Supported components

- Top taskbar (root, panels, every button)
- Flyout panels (Display, Sound, Wi-Fi, Bluetooth, Battery, Weather, Recycle Bin, Resource Monitor, Control Center, Media Player, System Tray, Notifications)
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
