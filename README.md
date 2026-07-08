# ConnectX

ConnectX is a real-time video conferencing platform that enables users to create or join meeting rooms for seamless peer-to-peer communication. It supports live audio and video streaming, in-meeting chat, and screen sharing using WebRTC, with Socket.IO handling signaling and room coordination.

## Overview

ConnectX is built using a Node.js backend and a React frontend, leveraging WebRTC for direct media transmission between participants.

The application consists of the following components:

- **client**: React application providing the video conferencing interface.
- **server**: Express and Socket.IO server responsible for room management, signaling, and participant coordination.
- **WebRTC layer**: Establishes peer-to-peer media connections between participants for low-latency communication.

## Features

- Create and join meeting rooms with unique room IDs.
- Real-time peer-to-peer video and audio communication.
- Multi-user conferencing support.
- Screen sharing during meetings.
- In-call text chat.
- Mute and unmute microphone.
- Toggle camera on and off.
- Responsive meeting interface.
- Automatic participant connection and disconnection handling.
- Low-latency communication by transmitting media directly between peers.

## Tech Stack

### Frontend

- React
- HTML5
- CSS3
- JavaScript
- WebRTC

### Backend

- Node.js
- Express.js
- Socket.IO

### Communication

- WebRTC
- Socket.IO Signaling

## Project Structure

```text
ConnectX/
├── client/
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── hooks/
│       ├── utils/
│       └── App.js
├── server/
│   ├── socket/
│   ├── routes/
│   ├── utils/
│   └── index.js
├── package.json
└── README.md
```

## Architecture

1. A user creates or joins a meeting room.
2. Socket.IO connects every participant to the signaling server.
3. The signaling server exchanges SDP offers, answers, and ICE candidates.
4. WebRTC establishes direct peer-to-peer media connections.
5. Audio, video, screen sharing, and chat are exchanged in real time between participants.

## How WebRTC Works

- Socket.IO is used only for signaling.
- Audio and video streams are transmitted directly between participants.
- ICE candidates establish the best available network path.
- After the peer connection is established, media no longer passes through the server, reducing bandwidth usage and latency.

## Getting Started

### Prerequisites

- Node.js (v18 or later)
- npm

### 1. Clone the repository

```bash
git clone https://github.com/prateekpaswan2001/ConnectX.git
cd ConnectX
```

### 2. Install dependencies

Install server dependencies.

```bash
cd server
npm install
```

Install client dependencies.

```bash
cd ../client
npm install
```

### 3. Configure environment variables

Create a `.env` file inside the server directory.

Example:

```env
PORT=5000
```

Add any additional environment variables required by your implementation.

### 4. Run the backend

```bash
cd server
npm start
```

### 5. Run the frontend

```bash
cd client
npm start
```

The application will be available at:

- Frontend: `http://localhost:3000`
- Backend: `http://localhost:5000`

## Building for Production

Frontend:

```bash
cd client
npm run build
```

Backend:

```bash
cd server
npm start
```

## Future Improvements

- Meeting recording
- Authentication
- Meeting scheduling
- Virtual backgrounds
- Participant permissions
- Waiting room support
- File sharing
- End-to-end encryption
- Adaptive video quality
- Mobile responsive improvements

## License

ISC
