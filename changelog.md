# Changelog

All notable changes to this **ASCII Geometry Dash** project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
