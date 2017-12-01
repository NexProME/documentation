# WebSocket Client

WebSocket clients work the same on the client side as the [server side](upgrade.md).

## Connecting a WebSocket client

WebSockets require an [URI](../http/uri.md) to connect to and an EventLoop to run on.

The `EventLoop` is described in [the async concepts introduction](../async/eventloop.md).

!!! warning
	Vapor does not retain the WebSocket. It is the responsibility of the user to keep the WebSocket active by means of strong references and pings.

```swift
let eventLoop: EventLoop = ...

let futureWebSocket: Future<WebSocket> = try WebSocket.connect(to: "ws://localhost/path", on: eventLoop)
```

## Using websockets

WebSockets are interacted with using [binary streams](binary-stream.md) or [text streams](text-stream.md).

All other information about websockets [is defined here.](websocket.md)