# WebSockets - Notes

## 1. What is WebSocket?
- **Definition:** WebSocket is a **bidirectional, full-duplex communication protocol** that enables real-time data exchange between a client and a server over a **single, persistent connection**.
- **Analogy:** Unlike HTTP (which is request-response based), WebSocket is like a **phone call**—once the connection is established, both parties can talk at any time.
- **Purpose:**
  - Enables **real-time applications** (e.g., chat apps, stock tickers, multiplayer games)
  - Reduces **network overhead** (no need to establish a new connection for each request)
  - More **efficient** than polling or long-polling

---

## 2. WebSocket Workflow
1. **Client initiates connection** via `ws://` or `wss://` (secure WebSocket).
2. **Handshake occurs** using an HTTP upgrade request (`Upgrade: websocket`).
3. **Persistent connection is established**, allowing **both client & server to send messages**.
4. **Either party can send/receive data asynchronously**.
5. **Connection remains open** until one side closes it.

---

## 3. WebSocket vs HTTP
| Feature      | HTTP (REST) | WebSocket |
|-------------|------------|-----------|
| Communication | Request-Response | Full-Duplex |
| Connection   | Opens & Closes per Request | Persistent |
| Latency     | Higher (due to reconnections) | Low |
| Ideal Use Cases | CRUD APIs, static data | Real-time updates, streaming |
| Data Format  | JSON, XML, HTML | JSON, Binary |

---

## 4. WebSocket URL Format
- **Standard WebSocket:** `ws://example.com/socket`
- **Secure WebSocket (TLS/SSL):** `wss://example.com/socket`

---

## 5. WebSocket Events
| Event      | Description |
|-----------|-------------|
| `onopen`  | Fired when the connection is established |
| `onmessage` | Triggered when a message is received |
| `onerror`  | Fired when an error occurs |
| `onclose`  | Triggered when the connection is closed |

---

## 6. Example: WebSocket Client (JavaScript)
```javascript
const socket = new WebSocket("wss://example.com/socket");

// When connection opens
socket.onopen = function () {
    console.log("Connected to WebSocket server");
    socket.send(JSON.stringify({ type: "hello", message: "Hello Server!" }));
};

// When receiving a message
socket.onmessage = function (event) {
    console.log("Message from server:", event.data);
};

// When an error occurs
socket.onerror = function (error) {
    console.error("WebSocket Error:", error);
};

// When the connection is closed
socket.onclose = function () {
    console.log("WebSocket connection closed");
};
