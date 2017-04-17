# WallPanel API

* [Configuration Settings](./configuration-settings.md)

## Commands
Command | Value | Example Payload | Description
-|-|-|-
clearCache | true | ```{"clearCache": true}``` | Clears the browser cache
evalJavaScript | Valid JavaScript | ```{"evalJavaScript": "alert('Hello World!');"}``` | Evaluates Javascript in the dashboard
relaunch | true | ```{"relaunch": true}``` | Relaunches the dashboard from configured launchUrl
reload | true | ```{"reload": true}``` | Reloads the current page immediately 
url | URL to Browse to | ```{"url": "http://<url>"}``` | Browse to a new URL immediately
wakeScreen | true/false | ```{"wakeScreen": true}``` | Wakes or sleeps the screen immediately

* Commands are constructed via valid JSON. It is possible to string multiple commands together:
  * eg, ```{"clearCache":true, "relaunch":true}```
* For REST, POST the JSON to URL ```http://[mywallpanel]/api/command```
* For MQTT, publish the JSON value to topic ```[baseTopic]/command```
  * Default: ```wallpanel/mywallpanel/command```


## State
Variable | Value | Example | Description
-|-|-|-
currentUrl | URL String | ```{"currentUrl":"http://hasbian:8123/states"}``` | Current URL the Dashboard is displaying

* State values are presented together as a JSON block
  * eg, ```{"currentUrl":"http://hasbian:8123/states"}```
* For REST, GET the JSON from URL ```http://[mywallpanel]/api/state```
* For MQTT, the state is published to topic ```[baseTopic]/state```
  * Default: ```wallpanel/mywallpanel/state```

## Sensors
...
