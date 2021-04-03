# As-WebSocket
**WebSocket bindings for AssemblyScript**

## Setting up

**Add --exportTable and --exportRuntime flags**

**Edit main file**

```js
// main.js

+ let wasmModule

+ const ws = require('as-websocket')

const imports = {
    ...ws.wasmImports
}

- const wasmModule = loader.instantaniateSync()

+ ws.wasmExports = wasmModule.exports

```

## Usage

**AssemblyScript WebSocket**

```js
import { WebSocket } from 'as-ws'

const socket = new WebSocket('ws://localhost:3000')
// Have a bug going for this :(

socket.on('message', (data) => {

    console.log('Message: ' + data)

})

socket.on('listening', () => {

    console.log('Listening')

})

socket.send('Hello From AssemblyScript!')

```

**Browser**

```html
<script src="https://unpkg.com/as-websocket@latest/browser.js"></script>
```