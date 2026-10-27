# Neon Blue theme for TopBar For Windows Mod

This Theme makes the Top Bar, Flyouts, Context menus, and Start Menu & Top Bar search Neon Blue.

**Author**: [WasiXGamer](https://github.com/wasixgamer)

![Screenshot](screenshot.png)


## Installation

To import the theme styles:

* Open the TopBar for Windows mod in Windhawk.
* Go to the "Settings" tab and select "Textual mode".
* Copy the content below to the text box and click "Save settings".

## Neon Blue (Full Width)
<details>
<summary>Content to import (click to expand)</summary>

```yaml

styleConstants:
  - 'ItemBackground=#274755'
  - 'ItemBorder=#397E9B'
  - 'IconColor=#4CC2FF'

controlStyles:
  - target: 'Grid#TopBarRoot'
    styles:
      - 'Background:=#242231'
      - 'CornerRadius=16'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=0'
      - 'IconColor=#00D6FF'
      - 'Height=40'

  - target: 'Button#ResourceButton, Button#WeatherButton, Button#MediaButton, Button#ClockButton, Button#AppTitleButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'Button#ResourceButton, Button#WeatherButton, Button#MediaButton, Button#ClockButton, Button#AppTitleButton'
    styles:
      - 'Margin=3,3,3,3'
      - 'VerticalAlignment=Center'
      - 'MinHeight=28'
      - 'Padding=8,0,8,0'
      - 'Foreground:=#E9F7FF'

  - target: 'Button#DisplayButton, Button#SoundButton, Button#WifiButton, Button#BluetoothButton, Button#BatteryButton, Button#RecycleBinButton, Button#SettingsButton, Button#ControlCenterButton, Button#NotificationsButton, Button#TrayIconButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=6'

  - target: 'Button#DisplayButton, Button#SoundButton, Button#WifiButton, Button#BluetoothButton, Button#BatteryButton, Button#RecycleBinButton, Button#SettingsButton, Button#ControlCenterButton, Button#NotificationsButton, Button#TrayIconButton'
    styles:
      - 'Margin=3,3,3,3'
      - 'MinWidth=30'
      - 'MinHeight=28'
      - 'VerticalAlignment=Center'
      - 'Padding=5,0,5,0'
      - 'Foreground:=$IconColor'

  - target: 'Button#SearchButton'
    styles:
      - 'Background:=Transparent'
      - 'BorderThickness=0'
      - 'Margin=3,2,3,2'
      - 'MinWidth=32'
      - 'MinHeight=28'
      - 'VerticalAlignment=Center'
      - 'Padding=4,0,4,0'
      - 'Foreground:=$IconColor'

  - target: 'Button#StartButton'
    styles:
      - 'Background:=Transparent'

  - target: 'StackPanel#TaskListPanel'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#TaskListPanel'
    styles:
      - 'Margin=0,3'
      - 'Padding=2,0,2,0'

  - target: 'Button#TaskButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Background:=Transparent'
      - 'CornerRadius=9'

  - target: 'TextBlock#ClockText, TextBlock#AppTitleText, TextBlock#TaskButtonText'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'Button#StartButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="40" Height="40" HorizontalAlignment="Center" VerticalAlignment="center" Margin="0,-5,0,0"><FontIcon FontFamily="Segoe UI Symbol" Glyph="&#x2744;" HorizontalAlignment="Center" VerticalAlignment="Center" /></Viewbox>'

  - target: 'Button#TrayIconButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="$IconColor" Data="M 3 6.5 L 21 6.5 L 12 18.25 Z" /></Grid></Viewbox>'

  - target: 'Button#DisplayButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 4.0 4.2 Q 11.4 3.6 19.7 4.3 Q 21.1 4.4 20.8 6.2 L 20.5 15.1 Q 20.4 16.8 18.8 16.6 L 4.6 16.5 Q 2.7 16.5 2.9 14.7 L 3.0 6.0 Q 2.8 4.3 4.0 4.2 Z M 11.6 16.8 L 11.8 20.5 M 7.4 20.8 Q 11.9 20.1 16.3 20.8 M 16.4 7.3 L 18.1 7.2 M 17.2 6.4 L 17.3 8.2" /></Grid></Viewbox>'

  - target: 'Button#SettingsButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 9.6 3.0 L 14.0 2.8 L 14.8 5.5 L 17.0 6.5 L 19.5 5.8 L 21.1 9.5 L 18.9 11.3 L 18.8 13.5 L 21.0 15.3 L 19.0 18.9 L 16.5 18.1 L 14.5 19.2 L 13.9 21.3 L 9.8 21.1 L 9.0 18.7 L 6.9 17.6 L 4.4 18.3 L 2.7 14.8 L 5.0 13.0 L 5.0 10.7 L 2.9 9.0 L 4.9 5.6 L 7.2 6.3 L 9.2 5.3 Z M 15.6 11.8 C 15.7 16.6 8.1 17.0 8.2 12.0 C 8.0 7.6 15.4 7.2 15.6 11.8 Z" /></Grid></Viewbox>'

  - target: 'Button#ControlCenterButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 4.2 3.0 Q 3.8 11.6 4.2 21.0 M 1.9 13.8 Q 4.2 14.2 6.3 13.8 M 11.8 3.1 Q 12.2 12.0 11.9 20.8 M 9.4 7.2 L 14.3 7.0 M 19.9 3.0 Q 19.4 11.5 19.9 21.0 M 17.4 16.1 L 22.0 15.8" /></Grid></Viewbox>'

  - target: 'Button#NotificationsButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 6.0 8.7 C 5.8 1.9 17.7 1.8 18.0 8.5 Q 17.5 13.3 20.7 16.7 Q 11.9 17.3 3.1 16.9 Q 6.3 13.1 6.0 8.7 Z M 9.8 20.0 Q 11.9 22.3 14.1 20.0 M 11.4 2.5 L 12.4 2.4" /></Grid></Viewbox>'

  - target: 'Button#SearchButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="$IconColor" Data="F0 M4 2 H14 V4 H16 V14 H14 V16 H4 V14 H2 V4 H4 Z M5 5 V13 H13 V5 Z M14 14 H17 V17 H20 V20 H17 V17 H14 Z" /></Grid></Viewbox>'

  - target: 'Canvas > FlyoutPresenter > Grid > Border#PART_BackgroundBorder'
    styles:
      - 'Background:=#242231'
      - 'Canvas.ZIndex=1'
      - 'CornerRadius=18'

  - target: 'FlyoutBlurHost'
    styles:
      - 'Background:=#242231'
      - 'CornerRadius=18'

  - target: 'StartMenuBlurHost, StartAccountSurface'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=16'

  - target: 'SearchBlurHost'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=18'

  - target: 'Border#SearchBarSurface'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'

  - target: 'Border#StartMenuSearchSurface'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'

  - target: 'TextBlock#FlyoutTitle'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'FlyoutFooterLink'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'FlyoutListRow, WifiNetworkRow, BluetoothDeviceRow, SearchResultRow, WeatherCityRow, TrayIconTile'
    styles:
      - 'Margin=0,3'
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WifiProgressRing, BluetoothProgressRing'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'WifiRefreshButton, BluetoothRefreshButton, WifiConnectButton, WifiCancelButton, WeatherPickerCancel, RecycleBinEmptyButton, RecycleBinCancelButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WifiPasswordBox, WeatherSearchBox'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Foreground:=#E9F7FF'

  - target: 'WifiHeaderToggle, BluetoothHeaderToggle'
    styles:
      - 'Foreground:=#E9F7FF'

  - target: 'MenuFlyoutPresenter'
    styles:
      - 'Background:=#242231'
      - 'Foreground:=#E9F7FF'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=12'

  - target: 'MenuFlyoutPresenter > Border#PART_BackgroundBorder, MenuFlyoutPresenter > Grid > Border#PART_BackgroundBorder'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'CornerRadius=12'

  - target: 'Button#ResourceCpuTab, Button#ResourceRamTab, Button#ResourceGpuTab'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=#00D6FF'
      - 'CornerRadius=10'

  - target: 'TextBlock#ResourceCpuTabText, TextBlock#ResourceRamTabText, TextBlock#ResourceGpuTabText'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'Border#InfoIsland'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'Border#ResourceGraphBorder'
    styles:
      - 'Background:=#1D2C3B'
      - 'CornerRadius=12'

  - target: 'Canvas#ResourceGraphCanvas > Polygon'
    styles:
      - 'Fill:=#34397E9B'

  - target: 'Canvas#ResourceGraphCanvas > Polyline'
    styles:
      - 'Stroke=#00C2E4'
      - 'StrokeThickness=2.2'

  - target: 'Grid#ResourceStatsGrid'
    styles:
      - 'Background:=$ItemBackground'
      - 'CornerRadius=12'
      - 'Padding=8,6,8,6'

  - target: 'TextBlock#StatLabel0, TextBlock#StatLabel1, TextBlock#StatLabel2, TextBlock#StatLabel3, TextBlock#InfoCpuLabel, TextBlock#InfoRamLabel, TextBlock#InfoGpuLabel'
    styles:
      - 'Foreground:=#A3C1CD'
      - 'FontSize=11'

  - target: 'TextBlock#StatValue0, TextBlock#StatValue1, TextBlock#StatValue2, TextBlock#StatValue3'
    styles:
      - 'Foreground:=#00D6FF'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'TextBlock#InfoCpuName, TextBlock#InfoRamName'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'ComboBox#GpuSelector'
    styles:
      - 'Background:=#1D2C3B'
      - 'Foreground:=#E9F7FF'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=8'

  - target: 'TextBlock#WeatherCityName'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'TextBlock#WeatherCurrentTemp'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontSize=38'
      - 'FontWeight=SemiLight'

  - target: 'TextBlock#WeatherDesc'
    styles:
      - 'Foreground:=#E9F7FF'

  - target: 'TextBlock#WeatherMinMax'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Button#WeatherDayButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=#00D6FF'
      - 'CornerRadius=12'

  - target: 'Button#WeatherDayButton > ContentPresenter > StackPanel > TextBlock[1]'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontWeight=SemiBold'

  - target: 'Button#WeatherDayButton > ContentPresenter > StackPanel > TextBlock[3]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Border#WeatherHourlyHost'
    styles:
      - 'Background:=#1D2C3B'
      - 'CornerRadius=12'

  - target: 'Border#WeatherHourlyCell'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Padding=0'

  - target: 'Border#WeatherHourlyCell > StackPanel'
    styles:
      - 'Background:=$ItemBackground'
      - 'Padding=2,8,2,8'
      - 'CornerRadius=9'

  - target: 'Border#WeatherHourlyCell > StackPanel > TextBlock[1], Border#WeatherHourlyCell > StackPanel > TextBlock[4]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Border#WeatherHourlyCell > StackPanel > TextBlock[3]'
    styles:
      - 'Foreground:=#00D6FF'
      - 'FontWeight=SemiBold'

  - target: 'Button#WeatherScrollLeft, Button#WeatherScrollRight'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=8'

  - target: 'Button#WeatherChangeLocation'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderThickness=0'
      - 'Foreground:=$IconColor'
      - 'CornerRadius=10'

  - target: 'Button#WeatherChangeLocation > ContentPresenter > TextBlock'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1]'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Border[1]'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > StackPanel > TextBlock[1]'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > StackPanel > TextBlock[2]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > Border[1]'
    styles:
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=9'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Border[1] > StackPanel > Grid > Button'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=8'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider'
    styles:
      - 'Foreground:=#00D6FF'
      - 'Background:=$ItemBorder'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Rectangle#HorizontalTrackRect'
    styles:
      - 'Fill:=$ItemBorder'
      - 'RadiusX=2'
      - 'RadiusY=2'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Rectangle#HorizontalDecreaseRect'
    styles:
      - 'Fill:=#00D6FF'
      - 'RadiusX=2'
      - 'RadiusY=2'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Thumb#HorizontalThumb'
    styles:
      - 'Background:=$IconColor'

  - target: 'StackPanel#ControlCenterFlyoutRoot > TextBlock'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Grid > Button'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Grid > Button > ContentPresenter > TextBlock'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontWeight=SemiBold'

  - target: 'QuickToggleTile, ControlCenterCustomizeButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'

  - target: 'MediaTransportButton'
    styles:
      - 'Background:=Transparent'
      - 'Foreground:=$IconColor'
      - 'CornerRadius=7'

  - target: 'MediaProgressBar'
    styles:
      - 'Foreground:=#00D6FF'
      - 'Background:=$ItemBorder'

  - target: 'MediaPositionText, MediaEndText, RecycleBinSizeText, RecycleBinCountText'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'RecycleBinConfirmButton'
    styles:
      - 'Background:=#48303E'
      - 'BorderBrush:=#FF8FA3'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Foreground:=#FF8FA3'

  - target: 'RecycleBinWarning'
    styles:
      - 'Foreground:=#FF8FA3'

  - target: 'NotificationsClearAllButton, NotificationsDoNotDisturbButton, NotificationShowMoreButton, OpenNativeNotificationsRow'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WindowsNotificationCard'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'NotificationCloseButton, NotificationCloseAppButton'
    styles:
      - 'Foreground:=#FF8FA3'
      - 'CornerRadius=8'

```
</details>

## Neon Blue (Island)

<details>
<summary>Content to import (click to expand)</summary>

```yaml

styleConstants:
  - 'ItemBackground=#274755'
  - 'ItemBorder=#397E9B'
  - 'IconColor=#4CC2FF'

controlStyles:
  - target: 'Grid#TopBarRoot'
    styles:
      - 'Background:=#242231'
      - 'CornerRadius=16'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=0'
      - 'IconColor=#00D6FF'
      - 'Height=40'
      - 'Width=Auto'

  - target: 'Button#ResourceButton, Button#WeatherButton, Button#MediaButton, Button#ClockButton, Button#AppTitleButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'Button#ResourceButton, Button#WeatherButton, Button#MediaButton, Button#ClockButton, Button#AppTitleButton'
    styles:
      - 'Margin=3,3,3,3'
      - 'VerticalAlignment=Center'
      - 'MinHeight=28'
      - 'Padding=8,0,8,0'
      - 'Foreground:=#E9F7FF'

  - target: 'Button#DisplayButton, Button#SoundButton, Button#WifiButton, Button#BluetoothButton, Button#BatteryButton, Button#RecycleBinButton, Button#SettingsButton, Button#ControlCenterButton, Button#NotificationsButton, Button#TrayIconButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=6'

  - target: 'Button#DisplayButton, Button#SoundButton, Button#WifiButton, Button#BluetoothButton, Button#BatteryButton, Button#RecycleBinButton, Button#SettingsButton, Button#ControlCenterButton, Button#NotificationsButton, Button#TrayIconButton'
    styles:
      - 'Margin=3,3,3,3'
      - 'MinWidth=30'
      - 'MinHeight=28'
      - 'VerticalAlignment=Center'
      - 'Padding=5,0,5,0'
      - 'Foreground:=$IconColor'

  - target: 'Button#SearchButton'
    styles:
      - 'Background:=Transparent'
      - 'BorderThickness=0'
      - 'Margin=3,2,3,2'
      - 'MinWidth=32'
      - 'MinHeight=28'
      - 'VerticalAlignment=Center'
      - 'Padding=4,0,4,0'
      - 'Foreground:=$IconColor'

  - target: 'Button#StartButton'
    styles:
      - 'Background:=Transparent'

  - target: 'StackPanel#TaskListPanel'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#TaskListPanel'
    styles:
      - 'Margin=0,3'
      - 'Padding=2,0,2,0'

  - target: 'Button#TaskButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Background:=Transparent'
      - 'CornerRadius=9'

  - target: 'TextBlock#ClockText, TextBlock#AppTitleText, TextBlock#TaskButtonText'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'Button#StartButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="40" Height="40" HorizontalAlignment="Center" VerticalAlignment="center" Margin="0,-5,0,0"><FontIcon FontFamily="Segoe UI Symbol" Glyph="&#x2744;" HorizontalAlignment="Center" VerticalAlignment="Center" /></Viewbox>'

  - target: 'Button#TrayIconButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="$IconColor" Data="M 3 6.5 L 21 6.5 L 12 18.25 Z" /></Grid></Viewbox>'

  - target: 'Button#DisplayButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 4.0 4.2 Q 11.4 3.6 19.7 4.3 Q 21.1 4.4 20.8 6.2 L 20.5 15.1 Q 20.4 16.8 18.8 16.6 L 4.6 16.5 Q 2.7 16.5 2.9 14.7 L 3.0 6.0 Q 2.8 4.3 4.0 4.2 Z M 11.6 16.8 L 11.8 20.5 M 7.4 20.8 Q 11.9 20.1 16.3 20.8 M 16.4 7.3 L 18.1 7.2 M 17.2 6.4 L 17.3 8.2" /></Grid></Viewbox>'

  - target: 'Button#SettingsButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 9.6 3.0 L 14.0 2.8 L 14.8 5.5 L 17.0 6.5 L 19.5 5.8 L 21.1 9.5 L 18.9 11.3 L 18.8 13.5 L 21.0 15.3 L 19.0 18.9 L 16.5 18.1 L 14.5 19.2 L 13.9 21.3 L 9.8 21.1 L 9.0 18.7 L 6.9 17.6 L 4.4 18.3 L 2.7 14.8 L 5.0 13.0 L 5.0 10.7 L 2.9 9.0 L 4.9 5.6 L 7.2 6.3 L 9.2 5.3 Z M 15.6 11.8 C 15.7 16.6 8.1 17.0 8.2 12.0 C 8.0 7.6 15.4 7.2 15.6 11.8 Z" /></Grid></Viewbox>'

  - target: 'Button#ControlCenterButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 4.2 3.0 Q 3.8 11.6 4.2 21.0 M 1.9 13.8 Q 4.2 14.2 6.3 13.8 M 11.8 3.1 Q 12.2 12.0 11.9 20.8 M 9.4 7.2 L 14.3 7.0 M 19.9 3.0 Q 19.4 11.5 19.9 21.0 M 17.4 16.1 L 22.0 15.8" /></Grid></Viewbox>'

  - target: 'Button#NotificationsButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="Transparent" Stroke="$IconColor" StrokeThickness="1.8" StrokeStartLineCap="Round" StrokeEndLineCap="Round" StrokeLineJoin="Round" Data="M 6.0 8.7 C 5.8 1.9 17.7 1.8 18.0 8.5 Q 17.5 13.3 20.7 16.7 Q 11.9 17.3 3.1 16.9 Q 6.3 13.1 6.0 8.7 Z M 9.8 20.0 Q 11.9 22.3 14.1 20.0 M 11.4 2.5 L 12.4 2.4" /></Grid></Viewbox>'

  - target: 'Button#SearchButton > ContentPresenter#ContentPresenter'
    styles:
      - 'Content:=<Viewbox Width="20" Height="20"><Grid Width="24" Height="24"><Path Fill="$IconColor" Data="F0 M4 2 H14 V4 H16 V14 H14 V16 H4 V14 H2 V4 H4 Z M5 5 V13 H13 V5 Z M14 14 H17 V17 H20 V20 H17 V17 H14 Z" /></Grid></Viewbox>'

  - target: 'Canvas > FlyoutPresenter > Grid > Border#PART_BackgroundBorder'
    styles:
      - 'Background:=#242231'
      - 'Canvas.ZIndex=1'
      - 'CornerRadius=18'

  - target: 'FlyoutBlurHost'
    styles:
      - 'Background:=#242231'
      - 'CornerRadius=18'

  - target: 'StartMenuBlurHost, StartAccountSurface'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=16'

  - target: 'SearchBlurHost'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=18'

  - target: 'Border#SearchBarSurface'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'

  - target: 'Border#StartMenuSearchSurface'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'

  - target: 'TextBlock#FlyoutTitle'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'FlyoutFooterLink'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'FlyoutListRow, WifiNetworkRow, BluetoothDeviceRow, SearchResultRow, WeatherCityRow, TrayIconTile'
    styles:
      - 'Margin=0,3'
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WifiProgressRing, BluetoothProgressRing'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'WifiRefreshButton, BluetoothRefreshButton, WifiConnectButton, WifiCancelButton, WeatherPickerCancel, RecycleBinEmptyButton, RecycleBinCancelButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WifiPasswordBox, WeatherSearchBox'
    styles:
      - 'Background:=#1D2C3B'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Foreground:=#E9F7FF'

  - target: 'WifiHeaderToggle, BluetoothHeaderToggle'
    styles:
      - 'Foreground:=#E9F7FF'

  - target: 'MenuFlyoutPresenter'
    styles:
      - 'Background:=#242231'
      - 'Foreground:=#E9F7FF'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=12'

  - target: 'MenuFlyoutPresenter > Border#PART_BackgroundBorder, MenuFlyoutPresenter > Grid > Border#PART_BackgroundBorder'
    styles:
      - 'Background:=#242231'
      - 'BorderBrush:=$ItemBorder'
      - 'CornerRadius=12'

  - target: 'Button#ResourceCpuTab, Button#ResourceRamTab, Button#ResourceGpuTab'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=#00D6FF'
      - 'CornerRadius=10'

  - target: 'TextBlock#ResourceCpuTabText, TextBlock#ResourceRamTabText, TextBlock#ResourceGpuTabText'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'Border#InfoIsland'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'Border#ResourceGraphBorder'
    styles:
      - 'Background:=#1D2C3B'
      - 'CornerRadius=12'

  - target: 'Canvas#ResourceGraphCanvas > Polygon'
    styles:
      - 'Fill:=#34397E9B'

  - target: 'Canvas#ResourceGraphCanvas > Polyline'
    styles:
      - 'Stroke=#00C2E4'
      - 'StrokeThickness=2.2'

  - target: 'Grid#ResourceStatsGrid'
    styles:
      - 'Background:=$ItemBackground'
      - 'CornerRadius=12'
      - 'Padding=8,6,8,6'

  - target: 'TextBlock#StatLabel0, TextBlock#StatLabel1, TextBlock#StatLabel2, TextBlock#StatLabel3, TextBlock#InfoCpuLabel, TextBlock#InfoRamLabel, TextBlock#InfoGpuLabel'
    styles:
      - 'Foreground:=#A3C1CD'
      - 'FontSize=11'

  - target: 'TextBlock#StatValue0, TextBlock#StatValue1, TextBlock#StatValue2, TextBlock#StatValue3'
    styles:
      - 'Foreground:=#00D6FF'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'TextBlock#InfoCpuName, TextBlock#InfoRamName'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'ComboBox#GpuSelector'
    styles:
      - 'Background:=#1D2C3B'
      - 'Foreground:=#E9F7FF'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=8'

  - target: 'TextBlock#WeatherCityName'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontSize=16'
      - 'FontWeight=SemiBold'

  - target: 'TextBlock#WeatherCurrentTemp'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontSize=38'
      - 'FontWeight=SemiLight'

  - target: 'TextBlock#WeatherDesc'
    styles:
      - 'Foreground:=#E9F7FF'

  - target: 'TextBlock#WeatherMinMax'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Button#WeatherDayButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=#00D6FF'
      - 'CornerRadius=12'

  - target: 'Button#WeatherDayButton > ContentPresenter > StackPanel > TextBlock[1]'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontWeight=SemiBold'

  - target: 'Button#WeatherDayButton > ContentPresenter > StackPanel > TextBlock[3]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Border#WeatherHourlyHost'
    styles:
      - 'Background:=#1D2C3B'
      - 'CornerRadius=12'

  - target: 'Border#WeatherHourlyCell'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Padding=0'

  - target: 'Border#WeatherHourlyCell > StackPanel'
    styles:
      - 'Background:=$ItemBackground'
      - 'Padding=2,8,2,8'
      - 'CornerRadius=9'

  - target: 'Border#WeatherHourlyCell > StackPanel > TextBlock[1], Border#WeatherHourlyCell > StackPanel > TextBlock[4]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'Border#WeatherHourlyCell > StackPanel > TextBlock[3]'
    styles:
      - 'Foreground:=#00D6FF'
      - 'FontWeight=SemiBold'

  - target: 'Button#WeatherScrollLeft, Button#WeatherScrollRight'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=8'

  - target: 'Button#WeatherChangeLocation'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderThickness=0'
      - 'Foreground:=$IconColor'
      - 'CornerRadius=10'

  - target: 'Button#WeatherChangeLocation > ContentPresenter > TextBlock'
    styles:
      - 'Foreground:=$IconColor'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1]'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Border[1]'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > StackPanel > TextBlock[1]'
    styles:
      - 'Foreground:=#E9F7FF'
      - 'FontWeight=SemiBold'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > StackPanel > TextBlock[2]'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Button[1] > ContentPresenter > StackPanel > Border[1]'
    styles:
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1'
      - 'CornerRadius=9'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Canvas > Grid > Border[1] > StackPanel > Grid > Button'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=8'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider'
    styles:
      - 'Foreground:=#00D6FF'
      - 'Background:=$ItemBorder'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Rectangle#HorizontalTrackRect'
    styles:
      - 'Fill:=$ItemBorder'
      - 'RadiusX=2'
      - 'RadiusY=2'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Rectangle#HorizontalDecreaseRect'
    styles:
      - 'Fill:=#00D6FF'
      - 'RadiusX=2'
      - 'RadiusY=2'

  - target: 'StackPanel#ControlCenterFlyoutRoot > * > Slider > * > Thumb#HorizontalThumb'
    styles:
      - 'Background:=$IconColor'

  - target: 'StackPanel#ControlCenterFlyoutRoot > TextBlock'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Grid > Button'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'StackPanel#ControlCenterFlyoutRoot > Grid > Button > ContentPresenter > TextBlock'
    styles:
      - 'Foreground:=$IconColor'
      - 'FontWeight=SemiBold'

  - target: 'QuickToggleTile, ControlCenterCustomizeButton'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'

  - target: 'MediaTransportButton'
    styles:
      - 'Background:=Transparent'
      - 'Foreground:=$IconColor'
      - 'CornerRadius=7'

  - target: 'MediaProgressBar'
    styles:
      - 'Foreground:=#00D6FF'
      - 'Background:=$ItemBorder'

  - target: 'MediaPositionText, MediaEndText, RecycleBinSizeText, RecycleBinCountText'
    styles:
      - 'Foreground:=#A3C1CD'

  - target: 'RecycleBinConfirmButton'
    styles:
      - 'Background:=#48303E'
      - 'BorderBrush:=#FF8FA3'
      - 'BorderThickness=1'
      - 'CornerRadius=10'
      - 'Foreground:=#FF8FA3'

  - target: 'RecycleBinWarning'
    styles:
      - 'Foreground:=#FF8FA3'

  - target: 'NotificationsClearAllButton, NotificationsDoNotDisturbButton, NotificationShowMoreButton, OpenNativeNotificationsRow'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=10'

  - target: 'WindowsNotificationCard'
    styles:
      - 'Background:=$ItemBackground'
      - 'BorderBrush:=$ItemBorder'
      - 'BorderThickness=1.3'
      - 'CornerRadius=12'

  - target: 'NotificationCloseButton, NotificationCloseAppButton'
    styles:
      - 'Foreground:=#FF8FA3'
      - 'CornerRadius=8'

```
</details>