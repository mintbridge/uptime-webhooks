Uptime Webhooks plugin
======================

This Uptime (https://github.com/fzaninotto/uptime) plugin notifies all configured events (up, down, paused, restarted) by sending a HTTP POST request to the given URL. The request will have a JSON payload of data from the event. Each event can have multiple hook URLs. URLs can be plain HTTP or HTTPS.

To use the plugin, first install it using npm while in the Uptime directory:

```sh
$ npm install uptime-webhooks
```

Then to enable it, add it to the `plugins/index.js`, as follows:

```js
// in plugins/index.js
exports.init = function() {
  require('uptime-webhooks').init();
}
```

Customize the settings in the `config/production.yaml` configuration file, adding a `webhooks` section, as in the example below:

```yaml
webhooks:
  event:
    up:
      - 'http://localhost:8082'
      - 'https://www.example.com/do/something'
    down:
      - 'https://www.example.com/warn/somebody'
    paused:
    restarted:
  dashboardUrl: 'http://localhost:8082'
```
