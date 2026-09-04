# The Windhawk TopBar Styling Guide

This guide provides a collection of styling customizations for the **TopBar for Windhawk** mod, a feature-rich top taskbar hosted by a dedicated Explorer tool process.

If you're not familiar with Windhawk, here are the steps for installing the mod:

- Download Windhawk from [windhawk.net](https://windhawk.net/) and install it.
- Go to "Mods" in the upper right menu.
- Find and install the **TopBar for Windhawk** mod.

After installing the mod, open its Settings tab and adjust the styles according to your preferences.

## Table of contents

* [Introduction](#introduction)
  * [Supported components](#supported-components)
  * [Finding targets](#finding-targets)
* [General](#general)
  * [Bar height](#bar-height)
  * [Bar background](#bar-background)
  * [Bar corner radius](#bar-corner-radius)
* [Task list](#task-list)
  * [Task button content](#task-button-content)
  * [Task button width](#task-button-width)
  * [Task icon size](#task-icon-size)
  * [Task button background](#task-button-background)
* [Control center](#control-center)
  * [Status buttons](#status-buttons)
  * [Flyout panels](#flyout-panels)
  * [Toggle switches](#toggle-switches)
  * [Slider styling](#slider-styling)
* [System tray](#system-tray)
  * [Tray panel](#tray-panel)
  * [Tray items](#tray-items)
* [Themes](#themes)
* [Colors](#colors)

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
