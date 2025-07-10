# Changelog

All notable changes to the **ASCII Geometry Dash** project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [v0.03-beta] - 07-10-2025

This update introduces updated an ball trajectory, support for multiple levels & exporting/importing .txt files as levels, and added functionality for the pink, red, and blue pads and orbs.

### Fixed:
- **Ball Trajectory:** The ball gamemode now has a more accurate trajcetory with an updated method of calculating the path.
- **Player Doesn't Disappear:** Thre player no longer disappears from the game wheb hitting specific orbs or pads. More info on this fix in *Added: Remaining Orb/Pad Functions*.

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
