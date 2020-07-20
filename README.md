# Webpack-web-ext-plugin

This plugin is intended to serve as a plugin for webpack-based web extension developing.

Desktop: watch, auto-reload

Android: choose device, watch, reload

## TODO

- [ ] Support web-ext build

## Usage

```bash
npm config set "@dimensiondev:registry" "https://npm.dimension.im"
npm install @dimensiondev/webpack-web-ext-plugin
```

Just add this to your webpack.config.js...

```javascript
const WebExtPlugin = require("@dimensiondev/webpack-web-ext-plugin");

config.plugins.push(
  // for Firefox
  new WebExtPlugin({ sourceDir: dist }),
  // for Firefox on Android
  new WebExtPlugin({ sourceDir: dist, target: "firefox-android" })
);
```

> This plugin takes all [CmdRunParams][1] and [CmdRunOptions][2] from `web-ext run`.
>
> You can customize it as much as your can.
>
> ...except `noReload` and `noInput` are enforced to `true` to work with webpack.

[1]: https://github.com/mozilla/web-ext/blob/e3f4d7f66416ae6bf7441541df145c306e53f848/src/cmd/run.js#L25
[2]: https://github.com/mozilla/web-ext/blob/e3f4d7f66416ae6bf7441541df145c306e53f848/src/cmd/run.js#L56
