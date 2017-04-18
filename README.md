# WallPanel API

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
TODO

Settings are documented under [Configuration Settings](./configuration-settings.md). 

Currently these are configured locally, but the API will develop means to work with configurations externally
