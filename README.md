# Adaptive Chess Master 🔥

A browser-based chess game where you can play against an AI with adaptive personalities, learn from your games, and track your progress. Built with HTML, CSS, and vanilla JavaScript, utilizing `sql.js` for in-browser database persistence.
![chess](https://github.com/user-attachments/assets/d4f18cb8-ed1d-47b7-a567-b2fa5c53b0c9)

*(Replace the placeholder above with an actual screenshot of your game!)*

## 🌟 Features

*   **Play Chess:** Standard chess rules implemented, including pawn promotion, castling, and en passant (simplified).
*   **Adaptive AI Opponent:**
    *   **Minimax Algorithm:** AI uses minimax with alpha-beta pruning for decision-making.
    *   **Configurable Difficulty:** Adjust AI thinking depth (1-4).
    *   **Multiple AI Personalities:**
        *   Adaptive (Default): Attempts to adjust to your play style.
        *   Aggressive Attacker
        *   Solid Defender
        *   Positional Strategist
        *   Mimic Player: Tries to copy your move patterns (conceptual).
        *   Counter Player: Tries to play moves that directly counter your last (conceptual).
    *   **Adaptation Speed:** Control how quickly the "Adaptive" AI changes its approach.
*   **Interactive UI:**
    *   Visually appealing chessboard with clear piece distinction.
    *   Click-to-select and click-to-move interface.
    *   Highlights for selected piece, valid moves, last move, and king in check.
    *   Display of captured pieces for both players.
    *   Game messages for turn indication, checks, and game over states.
*   **Real-Time Coach:**
    *   Toggleable coach that can provide move suggestions for the player (White).
    *   Coach advice displayed and optionally spoken.
*   **Voice Commands (Experimental):**
    *   Use voice to make moves (e.g., "move e2 to e4").
    *   Control game functions like "new game" or "toggle coach."
    *   Voice status displayed.
*   **Persistence & Learning (via `sql.js` & `localStorage`):**
    *   **Game Session Logging:** Records game start/end times, player color, AI settings, results, and player's opening sequence.
    *   **Move Logging:** Every move is recorded with FEN before/after, piece, squares, and flags (capture, check).
    *   **AI Settings Persistence:** Remembers your chosen AI personality, difficulty, and adaptation speed.
    *   **Achievements:** Earn badges for milestones (e.g., "First Win," "Five Victories").
*   **Gamification:**
    *   Track games won.
    *   View earned achievement badges.
*   **Post-Game Analysis & Replay:**
    *   Game over modal displaying result and basic analysis highlights.
    *   Conceptual strategy tips.
    *   **Replay Last Game:** Step through the moves of your most recently completed game.
*   **Match History:**
    *   View a list of recent games with results and AI opponent details.
    *   **Replay Specific Games:** Select any game from your history to replay its moves.
    *   Option to clear game history.
*   **Conceptual Visualizations:**
    *   UI toggles for "Board Control Heatmap" and "AI Move Prediction" (visual implementation pending).
*   **Responsive Design:** Adapts to different screen sizes for play on desktop or mobile browsers.
*   **Text-to-Speech:** Key game events and coach advice can be spoken aloud.

## 🚀 How to Play / Run

1.  **Download:**
    *   Simply download the `index.html` file (or clone this repository).
2.  **Open in Browser:**
    *   Open the `index.html` file in a modern web browser (e.g., Chrome, Firefox, Edge).
    *   No server is needed; it runs entirely client-side.
3.  **Play!**
    *   You play as White. Click a piece to select it, then click a valid destination square to move.
    *   Use the "New Game" button to start over.
    *   Explore the "Master Controls" panel on the right to adjust AI settings, toggle the coach, and view your stats.

All game data, including history and achievements, is stored in your browser's `localStorage`. Clearing your browser's site data for this page will erase your progress.

## 🎮 Controls

*   **Mouse:**
    *   Click your (White) pieces to select them. Valid moves will be highlighted.
    *   Click a highlighted valid move square to make the move.
    *   Click the selected piece again to deselect it.
*   **Buttons (Top of Game Area):**
    *   `New Game`: Starts a new chess match.
    *   `Toggle Coach`: Turns the real-time move suggestion coach ON or OFF.
    *   `🎤 (Voice Command)`: Activates listening for voice commands.
*   **Master Controls Panel (Right Side):**
    *   **AI Settings:**
        *   `AI Personality`: Choose the AI's play style.
        *   `AI Difficulty (Depth)`: Set how many moves ahead the AI thinks.
        *   `Adaptation Speed`: Adjust how quickly the "Adaptive" AI changes.
    *   **Visualizations (Conceptual):** Toggles for features not yet visually implemented.
    *   **Real-Time Coach:** Displays coach advice and voice command status.
    *   **Achievements:** Shows earned badges and game statistics.
    *   **Match History:** Lists recent games with replay options and a "Clear History" button.
*   **Post-Game Replay Controls (Appear after selecting replay):**
    *   `◀ Prev`: Go to the previous move in the replay.
    *   `Next ▶`: Go to the next move in the replay.
    *   `Exit Replay`: Return to the main game interface.

## 🛠️ Technical Details

*   **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6+).
*   **Database:** `sql.js` (SQLite compiled to WebAssembly) for in-browser database storage.
*   **Persistence:** Browser `localStorage` is used to store the `sql.js` database file.
*   **Chess Logic:** Custom-implemented chess rules, move generation, and game state management. The move generation (`getLegalMovesForPiece`) is currently a simplified pseudo-legal move generator and does not implement all subtleties of a full chess engine.
*   **AI:** Minimax algorithm with Alpha-Beta pruning.
*   **Speech:** Browser's Web Speech API (`SpeechRecognition` for input, `SpeechSynthesis` for output).

## 🔮 Future Enhancements

*   **Full Chess Engine Integration:** Replace custom chess logic with a more robust engine like Stockfish.js for perfect move validation and stronger AI.
*   **Implement Visualizations:** Actually draw the "Board Control Heatmap" and "AI Move Prediction" on the board.
*   **Puzzle Mode:** Add a section for chess puzzles.
*   **More Complex AI Adaptation:** Develop more sophisticated learning algorithms for the AI based on player history.
*   **Improved Opening Book:** Give the AI a more extensive repertoire of opening moves.
*   **Full Draw Condition Checks:** Implement threefold repetition and other less common draw rules.
*   **Enhanced Post-Game Analysis:** Provide more detailed feedback, identify blunders, good moves, etc.
*   **User Theming:** Allow users to choose different board and piece styles.

## ⚠️ Known Issues / Limitations

*   **Simplified Chess Logic:** The current move generation (`getLegalMovesForPiece`) is not a full legal move generator. It may miss some complex legal moves or allow some illegal ones in edge cases (especially around checks, pins, and king safety). This is the most significant limitation for serious chess play.
*   **Voice Commands:** Are experimental and highly dependent on browser support and microphone quality. Accuracy may vary.
*   **Performance:** AI at higher difficulty depths (especially depth 4+) can be slow as calculations are done in the browser.
*   **Conceptual Features:** Some UI elements (like visualization toggles) are placeholders for features not yet fully implemented visually.
*   **No Threefold Repetition:** This draw condition is not currently checked.

## 🤝 Contributing

Contributions are welcome! If you have ideas for improvements or bug fixes:
1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourAmazingFeature`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some YourAmazingFeature'`).
5.  Push to the branch (`git push origin feature/YourAmazingFeature`).
6.  Open a Pull Request.

Please report any bugs or suggest features by opening an issue.

## 📜 License

This project is open source. Feel free to use, modify, and distribute. If no specific license is attached, assume MIT or a similar permissive license unless stated otherwise by the original author.
(Consider adding a `LICENSE` file, e.g., MIT License).
```

**How to use this README:**

1.  Save the content above as `README.md` in the same directory as your `index.html` file.
2.  **Crucially, take a good screenshot of your game in action and replace the placeholder link:**
    `![Screenshot Placeholder](https://via.placeholder.com/800x500.png?text=Adaptive+Chess+Master+Game+Interface)`
    with something like:
    `![Adaptive Chess Master Screenshot](screenshot.png)` (and add `screenshot.png` to your project).
3.  If you decide on a specific open-source license (like MIT), create a `LICENSE` file with the license text and update the license section in the README.
4.  As you develop the game further (e.g., implement the conceptual visualizations), update the README to reflect those changes.
