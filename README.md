# WallPanel Common API

## Commands
Command | Value | Example Payload | Description
-|-|-|-
clearCache | true | ```{"clearCache": true}``` | Clears the browser cache
eval | Valid JavaScript | ```{"eval": "alert('Hello World!');"}``` | Evaluates Javascript in the dashboard
relaunch | true | ```{"relaunch": true}``` | Relaunches the dashboard from configured launchUrl
reload | true | ```{"reload": true}``` | Reloads the current page immediately 
url | URL to Browse to | ```{"url": "http://<url>"}``` | Browse to a new URL immediately
wake | true/false | ```{"wake": true}``` | Wakes or sleeps the screen immediately

* Commands are constructed via valid JSON. It is possible to string multiple commands together:
  * eg, ```{"clearCache":true, "relaunch":true}```
* For REST
  * POST the JSON to URL ```http://[mywallpanel]/api/command```
* For MQTT
  * WallPanel subscribes to topic ```[baseTopic]/command```
    * Default Topic: ```wallpanel/mywallpanel/command```
  * Publish a JSON payload to this topic

## State
Variable | Value | Example | Description
-|-|-|-
currentUrl | URL String | ```{"currentUrl":"http://hasbian:8123/states"}``` | Current URL the Dashboard is displaying

* State values are presented together as a JSON block
  * eg, ```{"currentUrl":"http://hasbian:8123/states"}```
* For REST
  * GET the JSON from URL ```http://[mywallpanel]/api/state```
* For MQTT
  * WallPanel publishes state to topic ```[baseTopic]/state```
    * Default Topic: ```wallpanel/mywallpanel/state```
  * The retain flag is used when publishing

## Sensors
TODO


## Configuration
Config Key | Value | Behavior | Default | Notes
-|-|-|-|-
app.deviceId | String | The unique identifier for this WallPanel device | mywallpanel |
app.preventSleep | true/false | Prevents the screen from turning off | false |
app.launchUrl | URL | The URL the Dashboard launches at | Tutorial Webpage | 
app.showActivity | true/false | On-screen indication of browser activity | true | 
camera.cameraId | int | The camera ID to attach to | 0 |
camera.motionEnabled | true/false | If the device camera is used for motion detection | false | 
camera.motionCheckInterval | int | The interval the camera is polled for motion in milliseconds | 500 |
camera.motionLeniency | int | The leniency on changes in pictures between polls | 20 |
camera.motionMinLuma | int | The minimum light needed to perform motion detection | 1000 |
camera.motionWake | true/false | If motion activity should wake the device | true |
camera.webcamEnabled | true/false | If the device camera is used as a webcam | false | *Planned*
http.enabled | true/false | Switch for REST(HTTP) being enabled | false | *Planned*
mqtt.enabled | true/false | Switch for MQTT being enabled | false | 
mqtt.serverName | String | The hostname/IP of the MQTT server | mqtt |  
mqtt.serverPort | Int | The port number for TCP MQTT | 1883 | 
mqtt.baseTopic | String | The root topic WallPanel will pub/sub under | wallpanel/{app.deviceId}/ | 
mqtt.clientId | String | The client ID to connect to MQTT with | {app.deviceId} | 
mqtt.username | String | The username to connect to MQTT with (or blank) | | 
mqtt.password | String | The password to connect to MQTT with (or blank) | |
mqtt.sensorFrequency | Int | The frequency to post sensor data in seconds, or 0 to never post | 0 |

TODO: Currently these are configured locally, but the API will develop means to work with configurations externally
