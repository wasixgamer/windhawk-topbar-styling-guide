# GreenBar theme for TopBar For Windows Mod

This Theme makes the TopBar Dark Green.

**Author**: [WasiXGamer](https://github.com/wasixgamer)

![Screenshot](screenshot.png)


## Installation

To import the theme styles:

* Open the TopBar for Windows mod in Windhawk.
* Go to the "Settings" tab and select "Textual mode".
* Copy the content below to the text box and click "Save settings".

<details>
<summary>Content to import (click to expand)</summary>

```yaml

controlStyles:
  - target: TopBarRoot, MenuFlyoutPresenter, FlyoutPresenter > Grid > Border#PART_BackgroundBorder
    styles:
      - Background:=#102A27
  - target: FlyoutBlurHost
    styles:
      - Background=transparent   
  - target: StartButton, SearchButton, ClockButton, DisplayButton, SoundButton, WifiButton, BatteryButton, BluetoothButton, TrayButton, TaskButton
    styles:
      - Background:=#27403C

```
</details>
