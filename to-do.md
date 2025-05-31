# Multiplayer Pong Game - To-Do List

**I. Project Initialization and Setup**

* - [x] 1.  Create Git Repository:
    * Create a new repository on your local machine or on a platform like GitHub.
    * Name the repository: `Multiplayer Pong Game`
    * Navigate into the newly created directory: `cd "Multiplayer Pong Game"` 
*  - [x] 2.  Project Directory Setup:
    * Create subdirectories: `backend`, `frontend`
*  - [x] 3.  Backend Setup (Node.js, TypeScript, Socket.IO):
    * `cd backend`
    * `npm init -y`
    * `npm install express socket.io cors`
    * `npm install -D typescript ts-node nodemon @types/node @types/express @types/socket.io`
    * Create `tsconfig.json` (adapt from Tic-Tac-Toe example, if helpful)
    * Update `package.json` scripts:
        ```json
        {
          "scripts": {
            "dev": "nodemon src/server.ts",
            "build": "tsc",
            "start": "node dist/server.js"
          }
        }
        ```
*  - [x] 4.  Frontend Setup (React, TypeScript, Socket.IO Client):
    * `cd ../frontend`
    * `npx create-react-app . --template typescript` OR `npm create vite@latest . -- --template react-ts`
    * `npm install socket.io-client`
*  - [x] 5.  Initial Commit:
    * `git init` (if you didn't initialize in step 1)
    * Create `.gitignore` (`node_modules`, etc.)
    * `git add .`
    * `git commit -m "Initial project setup"`
*  - [x] 6.  Core Planning:
    * **Backend:**
        * Basic server architecture, essential Socket.IO events (`connect`, `disconnect`, `paddle-move`, `ball-update`, `game-state`), core game state. Simplify if needed.
        * Game state should include player names.
        * Logic to handle player joining with a name.
        * Error handling for cases like "Player already in a game."
    * **Frontend:**
        * UI design for Lobby/Join screen (title, name input, join button, instructions).
        * UI design for Game screen (canvas, score display "First" vs "Second", "Leave" button, error display).
        * React components for Lobby and Game screens.

**II. Backend - Focus on Core**

*  - [ ] 7.  Server Setup (Express, CORS):
    * `backend/src/server.ts`: Express setup, CORS.
    * Basic "hello world" route.
*  - [ ] 8.  Socket.IO Integration:
    * Integrate Socket.IO with Express.
    * Handle `connect`, `disconnect` events.
    * Handle a new event for player joining with a name.
*  - [ ] 9.  Game Session Management:
    * Basic room creation.
    * Simple player pairing (e.g., first two join). Skip advanced matchmaking for now.
    * Handle player join/leave in rooms, including storing player names.
    * Send appropriate events/data to clients when a player joins.
*  - [ ] 10. Core Game State:
    * Data structure for: paddle positions, ball position, scores, **player names**.
    * Store/update state *on the server*.
*  - [ ] 11. Core Game Mechanics:
    * Simplified ball movement (basic velocity/direction).
    * Basic collision: ball/walls (top/bottom), ball/paddles. Basic scoring.
    * Paddle movement (from client).
*  - [ ] 12. Essential Socket.IO Events:
    * `game-start` (initial state, including player names).
    * `player-join` (event for player joining with name).
    * `paddle-move` (client to server).
    * `ball-update` (server to clients).
    * `game-state` (send entire game state).
    * `score-update` (server to clients).
    * `error` (for sending error messages).
    * Basic error handling (e.g., player already in game).
*  - [ ] 13. Basic Backend Testing:
    * Quick manual tests of server and Socket.IO. Focus on core functionality, including player joining and name handling.

**III. Frontend - Minimum Viable UI**

*  - [ ] 14. Essential UI Components:
    * `Lobby` (Join Screen):
        * Title, subtitle, name input, join button, instructions.
    * `GameCanvas` (basic `<canvas>` or SVG setup).
    * `Paddle` (simple rectangles).
    * `Ball` (simple circle/rectangle).
    * `Scoreboard` (display "First" vs "Second" with scores).
    * `LeaveButton`
    * `ErrorMessage` (for displaying errors from server).
*  - [ ] 15. Basic Rendering:
    * Draw paddles, ball, walls, and dotted line on `GameCanvas`. Static positions initially.
*  - [ ] 16. Player Input:
    * Capture keyboard input for *one* paddle.
    * Send `paddle-move` to server.
*  - [ ] 17. Socket.IO Integration (Frontend):
    * Connect to server.
    * Handle `game-start`, `ball-update`, `score-update`, `game-state`, and `error`.
    * Send `player-join` event with the player's name.
    * Switch between `Lobby` and `GameCanvas` components based on game state.
    * Update UI with player names, scores, and error messages.

**IV. Integration, Testing, Submission**

*  - [ ] 18. Integration Testing:
    * Test entire game flow, including player joining with names, switching screens, and error handling.
    * Test with *two* clients.
   * Basic error testing.
*  - [ ] 19. Critical Bug Fixes:
    * Address show-stopping issues.
*  - [ ] 20. Documentation:
    *Basic documentation.
*  - [ ] 21. Final Code Cleanup:
    * Remove debug code.
*  - [ ] 22. Final Submission Prep:
    * Package for submission.
