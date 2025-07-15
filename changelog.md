# Changelog

All notable changes to the **ASCII Geometry Dash** project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [v0.04-beta] - 07-14-2025

This update is pretty significant. Just read the stuffs below for this entry.

### Fixed:
- **Multi-character Object Parsing:** Fixed the odd placement of objects that are represented as multiple characters, such as "(gn)".
- **Mobile support:** Mobile is now fully supported, even in the editor.

### Added:
- **Level Editor:** This is one of the main focuses of this update. There is now a button in the Levels menu that opens the editor, which is filled with many, many features.

### Changed:
- **Levels Menu Layout:** Fefault/main levels and custom levels are now in separate tabs to make things more organized.

---

## [v0.03-beta] - 07-10-2025

This update introduces updated an ball trajectory, support for multiple levels & exporting/importing .txt files as levels, and added functionality for the pink, red, and blue pads and orbs.

### Fixed:
- **Ball Trajectory:** The ball gamemode now has a more accurate trajcetory with an updated method of calculating the path.
- **Player Doesn't Disappear:** Thre player no longer disappears from the game wheb hitting specific orbs or pads. More info on this fix in *Added: Remaining Orb/Pad Functions*.
 
### Changed:
- **Revamped Page Style:** The style for ASCII GD has been revamped to be more modern instead of the old bleak and boring style.

### Added:
- **Support For Multiple Levels:** There is now support for multiple levels, complete with a level menu that shows Default levels and Custom levels.
- **Level .TXT Import/Export:** You may now import .txt files to this progrsm to load an externally made level. You may also export any levels you have in your Custom levels list in the level menu.
- **Remaining Orb/Pad Functions:** Previously, the player woudl disappear when hitting an orb or pad with no code for its function. Every pink, yellow, red, and blue orb and pad function is now included in the code, preventing the player dissapearance bug.

---

## [v0.02-beta] - 07-09-2025

This update focuses on fixing the gravity portals and gravity switches.

### Fixed:
- **Gravity Switch Trajectory (Portal):** The gravity portals now cause an easing the the path trajectory instead of an instant fall.
- **Ground/Ceiling Gravity Swap Death:** Instead of dying immediately when landing on the top/bottom of a block after switching gravity, you can now safely land on it as solid ground.

### Changed
- **Extended Test Level:** The default test level (which is used to give an example of how to use the features fixed, fine-tuned, and added with each update after v0.01-beta) has been extended to include a usage of the gravity portals.

---

## [v0.01-beta] - 07-09-2025

Initial public release of the ASCII Geometry Dash engine.
