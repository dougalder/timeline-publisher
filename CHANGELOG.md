# Changelog

All notable changes to Timeline Publisher are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] — 2026-10-24

### Added
- **Vignette Effect**: Edge darkening effect for presentations and exports
  - Customizable darkness amount (0-100%)
  - Adjustable coverage size and softness
  - Frame shape control (square to circular)
  - Color presets (black, sepia, white) plus custom color picker
  - Toggle for including in videos and PNG frames
  - Keyboard shortcut: ⌘⇧V (macOS)
  - Full e2e test coverage for vignette rendering

- **3D Camera Improvements**
  - Perspective-correct label rendering in 3D mode
  - Improved label collision detection
  - Better depth handling for distant labels
  - Reduced visual jitter in event animations

- **Slideshow Enhancements**
  - Track-linked stops: stops now skip when their associated track is hidden
  - Clear visual indicators for skipped stops
  - Skip reason display ("Track is hidden")
  - Improved stop visibility logic

### Fixed
- **3D Perspective Distortion**: Lines now remain straight in 3D view
  - Implemented perspective-correct tessellation
  - Adaptive subdivision based on deviation from straight line
  - Improved visual quality of timeline geometry

- **Event Animation**: Removed distracting wiggle effect
  - Replaced with subtle ripple animation
  - Less intrusive during presentations
  - Better focus on content

- **File Associations**: CSV and project files now open correctly
  - Proper document type declarations in macOS app
  - File picker support for importing CSV data

### Changed
- **Default 3D Setting**: 3D view now defaults to "On the timeline" instead of off
- **Stop Timing**: Improved default values for hold and transition duration
- **UI Layout**: Vignette controls added to Slideshow tab with reveal toggle

### Technical
- Added perspective scaling calculations for 3D rendering
- Improved tessellation algorithm with sag detection
- Enhanced collision detection for label positioning
- All 33 e2e tests pass with vignette feature verification

## [1.0.0] — 2026-10-15

### Added
- **Complete native macOS app** with Electron
  - Menu bar integration with keyboard shortcuts
  - Window state persistence (size and position)
  - File dialogs for saving and exporting
  - Dock integration and file associations
  - "Show in Finder" for quick access to exports
  - Proper unsaved changes prompt

- **Core Timeline Features**
  - Interactive timeline visualization with pan and zoom
  - Color-coded tracks for event organization
  - Drag-and-drop CSV import
  - Built-in data table editor
  - Real-time editing with live timeline updates
  - Track visibility toggle

- **3D Visualization**
  - WebGL-based 3D timeline rendering
  - Fallback canvas-based 3D renderer for systems without WebGL
  - Camera controls: tilt, turn, zoom, focus, depth
  - Depth-based label scaling
  - Smooth perspective transformation

- **Slideshow & Presentation**
  - Create "stops" to guide viewers through timeline
  - Play/pause slideshow with smooth animations
  - Configurable stop timing (hold duration, transition speed)
  - Full-screen presentation mode
  - Keyboard navigation (next/previous stops)

- **Export & Publishing**
  - PNG frame export at configurable resolution
  - MP4 video export with adjustable FPS and resolution
  - CSV data export for backup
  - Web page publishing (HTML with read-only view)
  - File dialogs with "Save in Finder" integration

- **Data Import & Management**
  - CSV import with intelligent track detection
  - Support for TSV and TXT formats
  - Column mapping for Title, Start Date, End Date, Description
  - Batch event creation from spreadsheets

- **Styling & Customization**
  - Custom colors for tracks and events
  - Adjustable text labels and sizes
  - Light/dark theme toggle
  - Background customization (image, color, fill/fit)
  - Global zoom controls

- **Comprehensive Testing**
  - 33 end-to-end tests covering all major features
  - Playwright-based testing framework
  - Headless Linux testing support
  - Tests verify rendering, exports, file I/O, and UI

### Technical Stack
- Frontend: Pure HTML5, CSS3, JavaScript (no frameworks)
- Desktop: Electron 44.5.1
- Rendering: HTML5 Canvas + WebGL
- Testing: Playwright
- Build: npm and electron-packager
- Code Signing: Ad-hoc macOS code signing

### Known Limitations
- macOS only (1.0)
- WebGL required for full 3D performance (canvas fallback available)
- H.264 video codec requires Chrome/Chromium rendering engine

## Unreleased (Planned)

### Coming in Future Releases
- Linux and Windows support
- Mobile-responsive web version
- Advanced styling options (fonts, custom CSS)
- Multi-story projects
- Collaborative editing with cloud sync
- Template library for common timeline types
- Stock footage integration for videos
- Custom fonts and typography options
- Batch processing for multiple timelines
- Timeline comparison views
- Data import from more formats (Excel, Google Sheets, JSON APIs)

### Under Consideration
- Plugin system for custom effects
- Timeline branching and conditional flows
- Multi-view editing (outline, timeline, table simultaneously)
- Performance optimizations for 10,000+ events
- Accessibility improvements (screen reader support)
- Localization (multiple languages)

## [0.9.0] — 2026-10-01

### Added
- Initial web application implementation
- Basic timeline rendering
- Event creation and editing
- Simple slideshow functionality
- PNG export

---

## Version Numbering

- **Major** (X.0.0): Breaking changes, significant new features
- **Minor** (1.X.0): New features, backwards compatible
- **Patch** (1.0.X): Bug fixes, minor improvements

## How to Update

### For macOS App Users
1. Download the latest version from the [Releases](https://github.com/dougalder/timeline-publisher/releases) page
2. Open the `.dmg` file
3. Drag "Timeline Publisher" to Applications folder (or replace existing version)
4. Your existing projects automatically work with the new version

### For Web Version Users
Simply refresh the page to get the latest version (browsers automatically cache the HTML).

### For Developers
```bash
git checkout v1.1.0  # Check out a specific version
npm install
npm test
```

---

See the [README](README.md) for current features and the [Contributing Guidelines](CONTRIBUTING.md) for development information.
