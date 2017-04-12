# Configuration Settings
The configuration settings each app is currently capable of. This will be important when supporting centralized+common configurations in the future and understanding gaps

## Application
Config Name | Value | Android | iOS | Behavior
-|-|-|-|-
Start On Boot | bool | Yes | No(1) | Auto-starts app when device boots
Prevent WiFi Sleep | bool | Yes | No(1) | Prevents WiFi from sleeping
Prevent Screen Sleep | bool | Yes | | Prevents Screen from turning off (locking)

## Dashboard
Config Name | Value | Android | iOS | Behavior
-|-|-|-|-
Browser Engine | string (Auto*\|Native\|Legacy) | Yes | n/a | Enforces rendering engine
Auto-Launch | bool | Yes | Yes | The dashboard launches once immediately when the app starts
Launch URL | string | Yes | Yes | The URL the dashboard starts at
Page Load Progress | bool | Yes | | Displays an indicator of page load status

## MQTT
Config Name | Value | Android | iOS | Behavior
-|-|-|-|-
Enable MQTT | bool | Yes | Yes | Switch for MQTT support being enabled
Host (URL) | string | Yes | | The connection URL for MQTT
Hostname | string | | Yes | The hostname for TCP MQTT
Port | int | | Yes | The port number for TCP MQTT
Basic Topic | string | Yes | Yes | The root topic MQTT sub/pubs under
Client ID | string | | Yes | The Client ID to connect to MQTT with
Username | string | Yes | Yes | The username to authenticate to MQTT with, or blank for anonymous
Password | string(2) | Yes | Yes | The password for the username
Publish Frequency | int | Yes | | Publish frequency for sensor data, seconds

## Camera
Config Name | Value | Android | iOS | Behavior
-|-|-|-|-
Motion Detection | bool | Yes | | Switch for enabling Motion Detection wake
Check Interval | int | Yes | | The interval the camera is polled for motion, milliseconds
Leniency | int | Yes | | The leniency on changes in pictures between polls
Min Luma | int | Yes | | The minimum light needed to perform motion detection
Camera Selection | int | Yes | | Specify the device camera to monitor

## Sensors
Config Name | Value | Android | iOS | Behavior
-|-|-|-|-
Battery | bool | Yes | | Sample battery data
Pressure | bool | Yes | | Sample pressure data
Light | bool | Yes | | Sample light data

* (1) - May not be possible on iOS
* (2) - Masked in display
