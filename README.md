# Signaling Server for WebRTC Communication

## This signaling server facilitates WebRTC communication between peers by managing signaling messages and routing them appropriately.

## Features

### Socket.io Implementation: Utilizes Socket.io for real-time communication.

## Simple Configuration: Easily customizable to adapt to specific use cases.

### Prerequisites

#### Node.js installed on your system.

### Installation

## Clone this repository:

```js

git clone https://github.com/yourusername/signaling-server.git
```

## Navigate to the project directory:

```js
cd signaling-server

```

## Install dependencies:

```js

npm install
```

## Usage

### Set up the server by running the following command:

```js
node server.js
```

### The server will start running on the default port 5000 or a custom port specified in the process.env.PORT variable.

## Customization

### Changing Port: Modify the PORT variable in server.js to set a different port.

### Adjusting CORS Settings: Update the CORS configuration in the socket.io initialization to restrict origins or add more methods as needed.

## Signaling Events

### - makeCall: Initiates a call with another user.

### - answerCall: Responds to an incoming call.

### - IceCandidate: Exchange ICE candidates for WebRTC connectivity establishment.

## Connecting Clients

### Clients can connect to the signaling server using Socket.io and emit the above events to establish and manage WebRTC connections.

## Example:

```js
// Connect to signaling server
const socket = io("http://your-signaling-server-url");

// Emit a call
socket.emit("makeCall", { calleeId: "calleeUserId", sdpOffer: "sdpOfferData" });

// Handle incoming call
socket.on("newCall", (data) => {
  // Handle new call event
});

// Respond to a call
socket.emit("answerCall", {
  callerId: "callerUserId",
  sdpAnswer: "sdpAnswerData",
});

// Exchange ICE candidates
socket.emit("IceCandidate", {
  calleeId: "calleeUserId",
  iceCandidate: "iceCandidateData",
});
```

## License

### This project is licensed under the MIT License.
