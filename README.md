# Vpn Polybar
Upower module for polybar to get power state of your devices

## Dependencies
- Upower

## Configuration

You can change the threshold which define the high mid and low power status in `battery.sh` with this variables :
```sh
readonly HIGH_POWER=51
readonly MID_POWER=50
readonly LOW_POWER=20
```

## How it look

Example

High battery power : ![full](./.assets/full.png)

Medium battery power (<=50): ![mid](./.assets/mid.png)

Low battery power (<=20%) : ![full](./.assets/low.png)

## Usage

The script expects parameters :
 - `--is_device_connected [device_name]` : check if the device is connected, return exit code 1 if not connected instead of 0.
 - `--show_icon [device_name] [icon]` : show icon passed on parameter

### Example module for polybar

```ini
[module/g502-power]

type = custom/script
interval = 600
exec-if = ~/.config/polybar/scripts/battery.sh --is_device_connected G502
label-font = 7
exec = ~/.config/polybar/scripts/battery.sh --show_icon G502 

```