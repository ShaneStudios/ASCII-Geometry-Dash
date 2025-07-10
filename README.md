# ASCII Geometry Dash

Welcome to ASCII Geometry Dash, a playable web-based recreation of the core Geometry Dash physics engine, rendered entirely in ASCII characters. This project started as an in-depth research exploration into the game's physics and evolved into a flexible, data-driven game engine that runs in any modern browser.

This is a **work in progress**. While the core engine is stable, there may be bugs, and some features are still being polished. See the [Changelog](changelog.md) for version history.

## Features

*   **Authentic Physics Engine:** The engine is built on the verified physics constants of the original game, featuring a professional-grade, axis-separated collision system to prevent bugs. The physics are now calculated at 60 ticks per second for a smoother experience.
*   **Gamemode-Specific Physics:** Each gamemode (Cube, Ship, Ball, etc.) has its own, independently tuned set of physics constants for an authentic feel, including correct jump arcs and controllable ship flight.
*   **Full Orb & Pad Functionality:** Yellow, Pink, Red, and Blue orbs and pads are all implemented with their correct jump strengths and gravity-flipping mechanics.
*   **Modern UI & Level Management:**
    *   A sleek, responsive interface that works on both desktop and mobile.
    *   A slide-out menu for level selection.
    *   Separate lists for built-in and custom levels.
*   **Level Persistence and Sharing:**
    *   **Import:** Load custom levels from `.txt` files.
    *   **Export:** Save your creations to `.txt` files to share with others.
    *   **LocalStorage:** Your imported custom levels are saved in your browser so they are there when you come back.
*   **Text-Based Level Design:** Levels are designed using a simple, readable text format embedded directly in the HTML file. No external tools required!
*   **High-Fidelity ASCII Rendering:** Utilizes a tiny font size and a large character grid to create detailed shapes and smooth-feeling motion, with an optimized renderer that only updates changed characters.
*   **Accurate Hitboxes & Death Mechanics:** Implements nuanced hitboxes for spikes and authentic death conditions for each gamemode (e.g., cube dies on ceiling hit, ship does not). Includes a proper "death explosion" and automatic respawn cycle.

## How to Play

1.  **Download:** Download the `.html` file from this repository.
2.  **Open:** Open the file in any modern web browser (like Chrome, Firefox, or Safari).
3.  **Start:** Click the "Start" button to begin the level. You can select different levels from the menu (☰).
4.  **Control:**
    *   **Desktop:** Use the `Space Bar`, `Up Arrow`, or `Mouse Click` to jump or use your gamemode's ability.
    *   **Mobile:** Simply tap anywhere on the screen.
5.  **Reset:** If you die, the level will automatically restart after a short delay. You can also click the "Reset" button at any time to start over.

## Customization

One of the main goals of this project is to be easily customizable. All the logic, assets, and level data are contained within the single `.html` file.

### How to Create a Custom Level

Making your own level is the easiest way to customize the game.

1.  **Open the HTML File:** Open the `.html` file in a text editor (like VS Code, Sublime Text, or even Notepad).

2.  **Find `BUILT_IN_LEVELS`:** To edit the default levels, locate the `BUILT_IN_LEVELS` array in the `<script>` section. You can modify the `data` property of any level.

    ```javascript
    const BUILT_IN_LEVELS = [
        {
            name: "My New Level",
            data: `
    C...
    P...
    G...
    `
        }
    ];
    ```

3.  **Use the Key:** Use the following characters and codes to place objects.

| Code | Object | Description |
| :--- | :--- | :--- |
| `0` | Air | Empty space. |
| `P` | **Player Start** | The single, mandatory starting position. |
| `F` | Finish Line | Ends the level with a victory. |
| `B` | Block | A standard solid block. |
| `G` | Ground | Functionally the same as a block. |
| `C` | Ceiling | Functionally the same as a block. |
| `S` | Spike (Upright) | A normal spike. |
| `s` | Spike (Upside Down) | A spike on a ceiling. |
| `y` | Yellow Orb | Jump when tapped. |
| `Y` | Yellow Pad | Jump on contact. |
| `r` | Red Orb | Larger jump when tapped. |
| `R` | Red Pad | Larger jump on contact. |
| `(pj)` | Pink Orb | Smaller jump when tapped. |
| `(Pj)` | Pink Pad | Smaller jump on contact. |
| `(bg)` | Blue Orb | Flips gravity and `vy` when tapped. |
| `(Bg)` | Blue Pad | Flips gravity and `vy` on contact. |
| `1` | Cube Portal | Switches the player to Cube mode. |
| `2` | Ship Portal | Switches the player to Ship mode. |
| `3` | Ball Portal | Switches the player to Ball mode. |
| `4` | Wave Portal | _(Ready for implementation)_ |
| `(gn)` | Gravity Portal (Normal) | Sets gravity to normal (downward). |
| `(gr)` | Gravity Portal (Reverse) | Sets gravity to reversed (upward). |
| `.U` | **Upside Down Modifier** | Place after a code to flip it (e.g., `S.U` = `s`). |

4.  **Save and Play:** Save the `.html` file and open it in your browser to play your custom level! You can also use the **Import/Export** features in the in-game menu to manage levels as `.txt` files.

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
    1.  **Add to the Key:** Add a new entry in `TILE_MAP`.
        ```javascript
        const TILE_MAP = {
            // ...
            'g': { type: 'orb_green' },
            // ...
        };
        ```
    2.  **Add the Shape:** Add a corresponding entry in the `SHAPES` object.
    3.  **Add the Logic:** Go to the `handleInteractions()` function and add an `else if` condition to handle its specific gameplay logic.
        ```javascript
        else if (type === 'orb_green' && inputState.pressedThisFrame) {
            // ... your custom logic here ...
        }
        ```
*   **Tuning Physics:** The `PHYSICS` object contains all the constants for each gamemode. You can adjust values like `gravity`, `hSpeed`, and `jumpVelocity` here to change how the game feels.

## Contribution and Licensing

This project is open for anyone to use and modify. However, it is a personal project born from extensive research and effort.

**Please notify me, Shane Studios ([https://github.com/ShaneStudios](https://github.com/ShaneStudios)), before making any public forks or distributing modified versions of this code.** I would love to see what you create and collaborate if possible!

Thank you for checking out ASCII Geometry Dash.
