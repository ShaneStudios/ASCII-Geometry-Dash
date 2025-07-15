# ASCII Geometry Dash

Welcome to ASCII Geometry Dash, a playable web-based recreation of the core Geometry Dash physics engine, rendered entirely in ASCII characters. This project started as an in-depth research exploration into the game's physics and evolved into a flexible, data-driven game engine that runs in any modern browser.

This is a **work in progress**. While the core engine is stable, there may be bugs, and some features are still being polished. See the [Changelog](changelog.md) for version history.

## Features

*   **Authentic Physics Engine:** The engine is built on the verified physics constants of the original game, featuring a professional-grade, axis-separated collision system to prevent bugs. The physics are now calculated at 60 ticks per second for a smoother experience, and specifically tuned for Cube, Ship, Ball, Wave, and Robot gamemodes.
*   **Comprehensive Gamemode Support:** Full implementation of Cube, Ship, Ball, Wave, and Robot gamemodes, each with their unique movement, interaction, and gravity characteristics.
*   **Full Orb & Pad Functionality:** Yellow, Pink, Red, and Blue orbs and pads are all implemented with their correct jump strengths and gravity-flipping mechanics.
*   **Modern UI & Level Management:**
    *   A sleek, responsive interface that works on both desktop and mobile, including a mobile-specific landscape mode prompt.
    *   A slide-out menu for level selection, with separate tabs for built-in and custom levels.
*   **In-Game Level Editor:** Create, edit, and fine-tune your levels directly within the game! This powerful editor features:
    *   An intuitive grid-based interface for placing all game objects.
    *   Dedicated "Build" and "Edit" tools (move view, delete, add rows/columns).
    *   Unlimited undo and redo history for your edits.
    *   Auto-saving of your work to local storage for seamless continuation.
    *   Ability to name, save, and export levels directly from the editor.
    *   An in-editor icon legend and tips to guide you.
*   **Level Persistence and Sharing:**
    *   **Import:** Load custom levels from `.txt` files directly via the in-game menu.
    *   **Export:** Save your creations (or any custom level) to `.txt` files to share with others.
    *   **LocalStorage:** Your imported and custom-edited levels are saved in your browser so they are there when you come back.
*   **High-Fidelity ASCII Rendering:** Utilizes a tiny font size and a large character grid to create detailed shapes and smooth-feeling motion, with an optimized renderer that only updates changed characters.
*   **Accurate Hitboxes & Death Mechanics:** Implements nuanced hitboxes for spikes and authentic death conditions for each gamemode (e.g., cube dies on ceiling hit, ship does not). Includes a proper "death explosion" and automatic respawn cycle.

## How to Play

1.  **Download & Open:** Download the `.html` file from this repository and open it in any modern web browser (like Chrome, Firefox, or Safari).
2.  **Start:** Click the "Start" button to begin the level. You can select different levels from the menu (☰).
3.  **Control:**
    *   **Desktop:** Use the `Space Bar`, `Up Arrow`, or `Mouse Click` to jump or use your gamemode's ability.
    *   **Mobile:** Simply tap anywhere on the screen (ensure your device is in landscape mode).
4.  **Editor:** Access the level editor by clicking the "☰" button, then selecting the "New" button (or the "Edit" pencil icon next to an existing custom level). In the editor, click to place/delete objects and drag to pan the view.
5.  **Reset:** If you die, the level will automatically restart after a short delay. You can also click the "Reset" button at any time to start over.

## Customization

One of the main goals of this project is to be easily customizable. All the logic, assets, and level data are contained within the single `.html` file.

### How to Create & Edit Custom Levels

The easiest way to make your own levels is using the **in-game editor**!

1.  **Open the Menu:** Click the "☰" button in the game's UI.
2.  **Start Editing:**
    *   To create a **new level**, click the "New" button in the top right of the menu.
    *   To **edit an existing custom level**, navigate to the "Custom" levels tab and click the "Edit" (pencil) icon next to it.
3.  **Use the Editor:**
    *   The editor provides a grid for your level. Use the "Build" tab on the toolbar (or side-toolbar on mobile) to select objects.
    *   Click on a grid cell to place the selected object.
    *   Use the "Edit" tab for tools like "Move View" (to pan the grid) or "Delete" (to erase objects).
    *   You can also "Add Rows" or "Add Columns" to expand your level.
4.  **Save Your Work:** Remember to click "Save to Levels" in the editor header to add your creation to your custom levels list! Your work is also auto-saved to your browser.
5.  **Import/Export:** Use the "Import Level (.txt)" button in the main menu to load levels from files, or "Export .txt" in the editor to save your current level as a file for sharing.

Alternatively, for advanced users, levels are defined using a simple text format directly in the HTML file:

*   **Open the HTML File:** Open the `.html` file in a text editor (like VS Code, Sublime Text, or even Notepad).
*   **Find `BUILT_IN_LEVELS`:** To edit the default levels, locate the `BUILT_IN_LEVELS` array in the `<script>` section. You can modify the `data` property of any level.
*   **Use the Key:** Use the following characters and codes to place objects in the level data string.

| Code | Icon | Object | Description |
| :--- | :--- | :--- | :--- |
| `0` | - | Air | Empty space. |
| `P` | P | **Player Start** | The single, mandatory starting position. |
| `F` | F | Finish Line | Ends the level with a victory. |
| `B` | B | Block | A standard solid block. |
| `G` | G | Ground | Functionally the same as a block, usually for the bottom. |
| `C` | C | Ceiling | Functionally the same as a block, usually for the top. |
| `S` | S | Spike (Upright) | A normal spike. |
| `s` | s | Spike (Upside Down) | A spike on a ceiling. |
| `y` | y | Yellow Orb | Jump when tapped. |
| `Y` | Y | Yellow Pad | Jump on contact. |
| `r` | r | Red Orb | Larger jump when tapped. |
| `R` | R | Red Pad | Larger jump on contact. |
| `(pj)` | ⚪ | Pink Orb | Smaller jump when tapped. |
| `(Pj)` | ⬜ | Pink Pad | Smaller jump on contact. |
| `(bg)` | 🔵 | Blue Orb | Flips gravity and `vy` when tapped. |
| `(Bg)` | 🟦 | Blue Pad | Flips gravity and `vy` on contact. |
| `1` | 1 | Cube Portal | Switches the player to Cube mode. |
| `2` | 2 | Ship Portal | Switches the player to Ship mode. |
| `3` | 3 | Ball Portal | Switches the player to Ball mode. |
| `4` | 4 | Wave Portal | Switches the player to Wave mode. |
| `(gn)` | ↓ | Gravity Portal (Normal) | Sets gravity to normal (downward). |
| `(gr)` | ↑ | Gravity Portal (Reverse) | Sets gravity to reversed (upward). |
| `.U` | - | **Upside Down Modifier** | Place after a code to flip it (e.g., `S.U` becomes `s`). *Rarely needed with new separate codes.* |

*   **Save and Play:** Save the `.html` file and open it in your browser to play your custom level!

### Modifying the Code (Advanced)

If you want to add new objects, shapes, or game mechanics, you'll need to edit the core JavaScript objects.

*   **Adding New Shapes:** To change how an object looks, find the `SHAPES` object and edit the ASCII art for that object's key.
    ```javascript
    const SHAPES = {
        player: { cube:  ['NEW','ART'] },
        // ...
    };
    ```
*   **Adding New Objects:** To add a new type of object (e.g., a "Green Orb"):
    1.  **Add to the Map:** Add a new entry in `TILE_MAP` with a `type` and an `icon`.
        ```javascript
        const TILE_MAP = {
            // ...
            'g': { type: 'orb_green', icon: '🟢' },
            // ...
        };
        ```
    2.  **Add the Shape:** Add a corresponding entry in the `SHAPES` object (e.g., `orb_green: ['╭───╮','( G )','╰───╯']`).
    3.  **Add the Logic:** Go to the `handleInteractions()` function and add an `else if` condition to handle its specific gameplay logic.
        ```javascript
        else if (type === 'orb_green' && inputState.pressedThisFrame) {
            // ... your custom logic here ...
        }
        ```
    4.  **Add to Editor Toolbar:** If you want it in the in-game editor, you'll need to add its `token` to one of the `toolCategories` in the `setupEditor` function.
*   **Tuning Physics:** The `PHYSICS` object contains all the constants for each gamemode. You can adjust values like `gravity`, `hSpeed`, and `jumpVelocity` here to change how the game feels.

## Contribution and Licensing

This project is open for anyone to use and modify. However, it is a personal project born from extensive research and effort.

**Please notify me, Shane Studios ([https://github.com/ShaneStudios](https://github.com/ShaneStudios)), before making any public forks or distributing modified versions of this code.** I would love to see what you create and collaborate if possible!

Thank you for checking out ASCII Geometry Dash.
