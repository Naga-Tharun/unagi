# Unagi

> A *FRIENDS*-themed trivia game supporting single-player and real-time multiplayer modes with dynamic, AI-generated questions.

This repository contains the backend service: REST API + WebSocket server.

## Highlights

- **Realtime multiplayer:** Room-based session management using Socket.io. Players in the same room receive the same questions simultaneously, enabling low-latency competitive gameplay.
- **AI-generated content:** Integrated OpenAI's GPT API for on-demand question generation by category — no static question bank, infinite variety.
- **Stateful room lifecycle:** Room creation, player join / leave, and synchronised game state across concurrent connections.
- **Three game modes:** Single-player, multiplayer (free-for-all), team-player (two teams, turn-based).
- **Auth:** Token-based authentication for every gameplay endpoint.

## Tech stack

Node.js · Express · MongoDB · Socket.io · OpenAI GPT API · JWT

## Architecture (high level)

```
   Client  ──HTTPS──▶  Express API  ──▶  MongoDB
     │                      │
     └──WebSocket──▶ Socket.io server  ──▶  OpenAI GPT
```

## API reference

Full endpoint and socket documentation lives in [`docs/API.md`](./docs/API.md).

## Running locally

```bash
git clone https://github.com/Naga-Tharun/unagi.git
cd unagi
npm install
cp .env.example .env   # MONGO_URI, JWT_SECRET, OPENAI_API_KEY, PORT
npm start
```
