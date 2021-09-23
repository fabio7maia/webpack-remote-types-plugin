## Webpack5RemoteTypesPlugin

A webpack 5 plugin to download typescript type definitions generated by [dts-loader](https://github.com/ruanyl/dts-loader)
from remote.

The type packages only download one time, after initialization of webpack.

### Install

```
yarn add -D webpack5-remote-types-plugin
```

### Usage

```javascript
  new Webpack5RemoteTypesPlugin({
    remotes: {
      app: 'app@http://localhost:9000/remoteEntry.js',
    },
    outputDir: 'types', // supports [name] as the remote name
    remoteFileName: '[name]-dts.tgz' // default filename is [name]-dts.tgz where [name] is the remote name, for example, `app` with the above setup
  }),
```

The plugin will download tarball from `http://localhost:9000/app-dts.tgz` and unzip the tarball to `./types` folder
