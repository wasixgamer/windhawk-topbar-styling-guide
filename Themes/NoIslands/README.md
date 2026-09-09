# NoIslands theme for TopBar For Windows Mod

This Theme makes the TopBar not have the islands. It makes it cover full width and height of the grid.

**Author**: [WasiXGamer](https://github.com/wasixgamer)

![Screenshot](screenshot.png)


## Installation

To import the theme styles:

* Open the TopBar for Windhawk mod in Windhawk.
* Go to the "Settings" tab and select "Textual mode".
* Copy the content below to the text box and click "Save settings".

<details>
<summary>Content to import (click to expand)</summary>

```yaml

  controlStyles:
    - target: TopBarRoot
      styles:
        - Margin=0
        - CornerRadius=0

    - target: StartButton
      styles:
        - Background:=transparent

    - target: SearchButton
      styles:
        - Background:=transparent

    - target: ClockButton
      styles:
        - Background:=transparent

    - target: DisplayButton
      styles:
        - Background:=transparent

    - target: SoundButton
      styles:
        - Background:=transparent

    - target: WifiButton
      styles:
        - Background:=transparent

    - target: BluetoothButton
      styles:
        - Background:=transparent
    - target: BatteryButton
      styles:
        - Background:=transparent
    - target: TrayButton
      styles:
        - Background:=transparent

    - target: TaskButton
      styles:
        - Background:=transparent

```
</details>
