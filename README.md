# Bomberman-DOM 💣

A real-time, multiplayer Bomberman clone built with Node.js, WebSockets, and a custom lightweight vanilla JavaScript frontend framework. 

## 🌟 Features

- **Real-Time Multiplayer:** Play with up to 4 players simultaneously in a fast-paced arena using WebSocket technology.
- **Custom Frontend Framework:** Features a custom-built, virtual DOM-like framework (`framework.js`) for efficient UI rendering, state management, and component updates.
- **Classic Game Mechanics:** Grid-based movement with destructible blocks, solid walls, power-ups, and a lives system.
- **Interactive Lobby:** Includes a waiting room with a countdown timer to gather players before the match begins.
- **Live Chat System:** Communicate with other players via an integrated chat box available in both the lobby and the active game screen.
- **Responsive UI:** A modern, card-based interface with dynamic views (Main Menu, Waiting Room, Game Screen, and Game Over).

## 📖 Documentation

For more detailed information, please refer to the following documents:
- [Installation and Setup](INSTALL.md)
- [How to Play](HOW_TO_PLAY.md)
- [Architecture & Project Structure](ARCHITECTURE.md)

# Installation and Setup

Follow these steps to get a local instance of Bomberman-DOM up and running.

## 📋 Prerequisites

- [Node.js](https://nodejs.org/) (v10.0.0 or higher recommended)

## 🚀 Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd bomberman-dom
   ```
2. **Install dependencies:**
This project relies on the `ws` package for WebSockets.
```bash
npm install
```

3. **Start the server:**
```bash
node server.js
```

4. **Access the game:**
Open your web browser and navigate to `http://localhost:8888`.
*(Note: To test the multiplayer functionality locally, simply open multiple browser tabs or separate windows to the same local address).*

# How to Play

Welcome to the arena! Here is everything you need to know to survive and win.

## 🎮 Controls

- **Movement:** `W`, `A`, `S`, `D` or `Arrow Keys`
- **Place Bomb:** `Spacebar`
- **Toggle Chat:** `C` 

## 🎯 Objective

Enter your name to join the lobby. Once the game starts, navigate the maze, destroy wooden blocks to uncover power-ups, and strategically place bombs to trap and eliminate your opponents. 

You start with 3 lives. Be the last player standing to win!

## ⭐ Power-Ups

By destroying blocks, you may uncover power-ups to enhance your character:
- **Bomb:** Increases the maximum number of bombs you can drop at once.
- **Flame:** Increases the blast radius of your explosions.
- **Speed:** Increases your movement speed.

# Architecture & Project Structure

## 🛠️ Technologies Used

- **Backend:** Node.js, `ws` (WebSocket library for real-time bidirectional communication), native HTTP module for static file serving.
- **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6 Modules).
- **Architecture:** Client-Server model where the server is authoritative over the game state (handling collision detection, damage, and timers).

## 📂 Directory Layout

- `server.js`
  The backend Node.js server. It handles static file delivery and the core WebSocket multiplayer game logic (player states, bomb timers, explosion hitboxes).

- `public/index.html`
  The main HTML entry point for the frontend.

- `public/index.js`
  The frontend application logic. Handles the game loop, keyboard inputs, WebSocket message parsing, and renders different screens using the custom framework.

- `public/src/framework.js`
  A custom, lightweight frontend framework. It provides `createElement` functionality, virtual DOM rendering, and a state manager with publish/subscribe capabilities.

- `public/styles/`
  Contains all styling and visual assets.
  - `style.css`: Main stylesheet.
  - `/svg/` & Images: Game assets including sprites, SVGs (bombs, walls, players), and GIFs.
