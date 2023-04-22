<p align="center">
  <img src="https://avatars0.githubusercontent.com/u/24429466?s=200&u=031180a39da9253ac73d782dabb27d46cf828e37&v=4">
</p>
<p align="center">
  A WebSocket client for building WeChat Mini Program implement by <a href="https://socket.io/">socket.io</a>
</p>
<p align="center">
  <a href="https://www.npmjs.com/package/weapp.socket.io">
    <img src="https://img.shields.io/badge/npm-2.0.1-brightgreen.svg">
  </a>

  <a href="https://github.com/weapp-socketio/weapp.socket.io/network">
    <img src="https://img.shields.io/github/forks/10cella/weapp.socket.io.svg">
  </a>  
  
  <a href="https://github.com/weapp-socketio/weapp.socket.io/stargazers">
    <img src="https://img.shields.io/github/stars/10cella/weapp.socket.io.svg">
  </a>  
  
  <a href="https://github.com/weapp-socketio/weapp.socket.io/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/10cella/weapp.socket.io.svg">
  </a>

  <a href="https://github.com/weapp-socketio/weapp.socket.io/issues">
    <img src="https://img.shields.io/github/issues/10cella/weapp.socket.io.svg">
  </a>
</p>


## Feature

Full feature socket.io style implemented, based-on `socket.io@3.x` version, such as:
- send message queue
- auto reconnect
- ping, pong
- room, namespaces

## Platform Support
  - 微信
  - 支付宝

## Demos

[Official Framework](https://github.com/wxsocketio/socket.io-weapp-demo) , [Wepy Framework](https://github.com/weapp-socketio/wepy-demo-socket.io)

## Install

If you use a third-party framework such as [wepy](https://github.com/Tencent/wepy), you should install via `npm`

```
$ npm install weapp.socket.io
```

Or if you use the native way to write code，I recommend using `git clone`

```
$ git clone https://github.com/weapp-socketio/weapp.socket.io

# development mode
$ npm run build-dev:wechat

# production mode
$ npm run build:wechat

# build 
npm run prepublish

$ cp path/weapp.socket.io/dist/weapp.socket.io.js path/your_weapp_dir
```

## Using with socket.io v4, e.g. v4.6.1

Use v4.1.3 of socket.io-client. But the javascript will have error when running in Wechat Devtools, we must change the `mode` to `none` int the `webpack.config.js`. Once the javascript is produced, minify it with [terser](!https://github.com/terser/terser), we cannot use `-m` as it will produce error. 

```
terser weapp.socket.io.wx.js -p bare_returns -c -o weapp.socket.io.js
```


Note: I have tried many compressor, only this one is working fine.

```json
  "dependencies": {
    "socket.io-client": "4.1.3"
  },
```

## Usage

code style is same to [socket.io-client](https://github.com/socketio/socket.io-client)

```
const io = require('./yout_path/weapp.socket.io.js')

const socket = io('https://socket-io-chat.now.sh')

socket.on('connect', () => {
  console.log('connection created.')
});

socket.on('new message', d => {
  const {
    username,
    message
  } = d;
  console.log('received: ', username, message)
});

socket.emit('add user', "Jack");
```

## API

See [socket.io-client API](https://github.com/socketio/socket.io-client/blob/master/docs/API.md)

## Contributors

### Code Contributors

This project exists thanks to all the people who contribute. [[Contribute](.github/CONTRIBUTING.md)].
<a href="https://github.com/weapp-socketio/weapp.socket.io/graphs/contributors"><img src="https://opencollective.com/weappsocketio/contributors.svg?width=890&button=false" /></a>

### Financial Contributors

Become a financial contributor and help us sustain our community. [[Contribute](https://opencollective.com/weappsocketio/contribute)]
