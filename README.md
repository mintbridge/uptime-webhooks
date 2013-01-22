Uptime Webhooks plugin

This Uptime (https://github.com/fzaninotto/uptime) plugin notifies all configured events (up, down, paused, restarted) by sending a HTTP POST request to the given URL. The request will have a JSON payload of data from the event. Each event can have multiple hook URL's

To use the plugin first install it using: ```npm install uptime-webhooks```. Then to enable it, add it to your Uptime plugins config, see the example below:

Example configuration

```
plugins:
  webhooks:
    event:
      up:
        - 'http://localhost:8082'
        - 'http://www.example.com/do/something'
      down:
        - 'http://www.example.com/warn/somebody'
      paused:
      restarted:
    dashboardUrl: 'http://localhost:8082'
```
