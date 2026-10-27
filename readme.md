DEPTH (Глубина) — 3D Battleship

Version: 0.91
Date: 2026-10-27

=== OVERVIEW ===

Depth is a three-dimensional Battleship game played on a 6 × 6 × 4 grid.
Two players connect directly via WebRTC (manual signaling by exchanging
copy-pasted offer/answer text). No server is required.

The game is built with Three.js for 3D rendering and uses a peer-to-peer
data channel for all game communication.

=== GAME RULES ===

- The board is a 3D grid of 6 (X) × 6 (Y) × 4 (Z) cells.
- Each player places a fleet of 5 ships with lengths: 4, 3, 3, 2, 2.
- Ships are placed along one of the three axes (X, Y, or Z).
- Ships cannot overlap or extend outside the board.
- Players take turns firing at a single cell on the opponent's board.
- A shot is either a hit or a miss.
- The first player to sink all opponent ships wins.

=== HOW TO PLAY ===

1. Open the game in a browser (HTTPS or localhost required for WebRTC).
2. One player clicks "Create Game" (host), the other clicks "Join by Invitation" (guest).
3. Host copies the generated invitation and sends it to the guest.
4. Guest pastes the invitation, clicks "Create Answer", copies the answer,
   and sends it back to the host.
5. Host pastes the answer and clicks "Apply Answer".
6. Once the connection is open, both players proceed to fleet placement.
7. During placement:
   - Select an axis (X, Y, or Z).
   - Click a cell to place the current ship starting at that cell.
   - Drag with the mouse to rotate the 3D view.
   - Place all 5 ships, then click "Ready".
8. The host starts the game when both fleets are submitted.
9. During the game:
   - Use "Target" view to see the opponent's board and click a cell to fire.
   - Use "My Fleet" view to see your own board and incoming shots.
   - Turns alternate automatically.
10. The game ends when one player sinks the entire enemy fleet.

=== MULTIPLAYER ===

- Connection type: WebRTC data channel (peer-to-peer).
- Signaling: manual copy-paste of SDP offer/answer (no signaling server).
- STUN server: stun:stun.l.google.com:19302.
- Both players must use HTTPS or localhost for WebRTC to work.

=== TECHNICAL STACK ===

- Three.js (r170) for 3D rendering.
- OrbitControls for camera rotation.
- WebRTC DataChannel for network communication.
- Vanilla JavaScript (ES modules), HTML, CSS.

=== CHANGELOG ===

v0.91 (2026-10-27)
- Initial release.
- 3D Battleship on a 6 × 6 × 4 grid.
- Fleet composition: 4, 3, 3, 2, 2.
- Manual WebRTC signaling via copy-paste.
- Host-authoritative game logic.
- 3D board with orbit controls.
- Fleet placement along X, Y, Z axes.
- Target and own-fleet views.
- Turn-based shooting and win detection.
- Result screen with victory/defeat message.