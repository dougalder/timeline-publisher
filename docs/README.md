# Documentation

Complete documentation for Timeline Publisher users and developers.

## For Users

Start here based on what you need:

### Getting Started
- **[Installation Guide](INSTALL.md)** — Download, install, and run Timeline Publisher
- **[Quick Start](../README.md)** — First steps and basic concepts

### Learning
- **[User Manual](MANUAL.md)** — Complete feature guide with workflows
  - Data import and management
  - Timeline visualization and navigation
  - 3D view and controls
  - Creating slideshows
  - Vignette effect
  - Exporting and publishing
  
### References
- **[Keyboard Shortcuts](KEYBOARD-SHORTCUTS.md)** — All keyboard commands
- **[CSV Format Guide](CSV-FORMAT.md)** — How to prepare your data
- **[FAQ](FAQ.md)** — Answers to common questions

### Project Files
- **[Project Format](../README.md#project-format)** — JSON structure for saved projects

---

## For Developers

### Setup
- **[Installation Guide - Building from Source](INSTALL.md#building-from-source)** — Set up development environment
- **[Directory Structure](../DIRECTORY_STRUCTURE.md)** — Repository layout and file descriptions

### Contributing
- **[Contributing Guidelines](../CONTRIBUTING.md)** — How to contribute code and improvements
- **[Development Workflow](../CONTRIBUTING.md#development-workflow-details)** — Code style, branching, testing

### Technical

#### Architecture
- [README - Architecture](../README.md#architecture) — Tech stack overview
- [main.js Overview](../CONTRIBUTING.md#key-files-to-understand) — Electron main process
- [preload.js Overview](../CONTRIBUTING.md#key-files-to-understand) — Security bridge

#### Code

**Main Application** (`app/index.html`):
- UI layout and controls (HTML/CSS)
- Timeline rendering engine
- 3D visualization and WebGL
- Data table editor
- CSV import/export
- Video export pipeline
- Project save/load

**Key Functions**:
- `renderScene()` — 2D timeline rendering
- `render3D()` — 3D perspective rendering
- `buildTL()` — Build timeline data structure
- `playSlideshow()` — Slideshow playback
- `exportMP4()` — Video rendering

**Electron App** (`main.js`, `preload.js`, `build.mjs`):
- Window management
- Menu bar implementation
- File dialogs and I/O
- Code signing and packaging

#### Testing
- **[Test Guide](../CONTRIBUTING.md#testing)** — How tests work
- `tests/e2e.mjs` — 33 comprehensive end-to-end tests
- Coverage: Import, editing, 3D, video export, saves, unsaved changes

---

## Documentation Structure

```
docs/
├── README.md                 ← You are here
├── MANUAL.md                 # User guide (20+ KB)
├── INSTALL.md                # Installation & building
├── KEYBOARD-SHORTCUTS.md      # Shortcut reference
├── CSV-FORMAT.md              # Data format guide
├── FAQ.md                     # Q&A (50+ answers)
└── screenshots/               # Documentation images
    ├── app-interface.png
    ├── 3d-view.png
    └── ...
```

---

## Quick Navigation

### "How do I...?"

- **...install Timeline Publisher?** → [Installation Guide](INSTALL.md)
- **...import my data?** → [CSV Format Guide](CSV-FORMAT.md)
- **...use 3D mode?** → [Manual › 3D View](MANUAL.md#3d-view)
- **...create a slideshow?** → [Manual › Creating Slideshows](MANUAL.md#creating-slideshows)
- **...export as video?** → [Manual › MP4 Video Export](MANUAL.md#mp4-video-export)
- **...publish to web?** → [Manual › Web Publishing](MANUAL.md#web-publishing)
- **...build from source?** → [Installation Guide › Building from Source](INSTALL.md#building-from-source)
- **...report a bug?** → [GitHub Issues](https://github.com/dougalder/timeline-publisher/issues)

### "What is...?"

- **...a Track?** → [Manual › Understanding Tracks](MANUAL.md#understanding-tracks)
- **...a Stop?** → [Manual › Understanding Stops](MANUAL.md#understanding-stops)
- **...vignette?** → [Manual › Vignette Effect](MANUAL.md#vignette-effect)
- **...3D view?** → [Manual › 3D View](MANUAL.md#3d-view)
- **...the project format?** → [README › Project Format](../README.md#project-format)

### Troubleshooting

- **App won't launch** → [Installation › Troubleshooting](INSTALL.md#troubleshooting)
- **CSV import issues** → [CSV Format › Troubleshooting](CSV-FORMAT.md#troubleshooting)
- **3D view problems** → [FAQ › 3D View](FAQ.md#3d-view)
- **Export issues** → [FAQ › Exporting & Publishing](FAQ.md#exporting--publishing)

---

## Keeping Docs Updated

When modifying Timeline Publisher:

1. **Change a feature** → Update relevant section in `MANUAL.md`
2. **Add keyboard shortcut** → Add to `KEYBOARD-SHORTCUTS.md`
3. **Fix data format** → Update `CSV-FORMAT.md` if needed
4. **Answer FAQ** → Add Q&A to `FAQ.md`
5. **Change version** → Update `../CHANGELOG.md`
6. **Add files** → Update `../DIRECTORY_STRUCTURE.md`

---

## Doc Sections

### MANUAL.md (User Guide)
1. Getting Started
2. Creating Your First Timeline
3. Importing Data
4. Data Management
5. Timeline Visualization
6. 3D View
7. Styling & Appearance
8. Creating Slideshows
9. Vignette Effect
10. Exporting & Publishing
11. Menu Reference
12. Tips & Tricks
13. Keyboard Shortcuts Summary
14. Troubleshooting

### INSTALL.md (Setup & Building)
1. macOS Desktop App
2. Web Version
3. Building from Source
4. Building macOS Package
5. Docker / Container Deployment
6. Deployment to Website
7. Troubleshooting

### KEYBOARD-SHORTCUTS.md (Reference)
1. macOS Shortcuts (File, Edit, View, Slideshow)
2. Web Version Shortcuts
3. Touch & Trackpad
4. In-App Navigation
5. Customizing Shortcuts
6. Accessibility
7. Reference Card
8. Power User Tips

### CSV-FORMAT.md (Data Import)
1. Basic Format
2. Required & Optional Columns
3. Date Formats
4. CSV Examples
5. Column Headers
6. Tips for Clean Data
7. Empty Fields
8. Special Characters
9. Size & Performance
10. Troubleshooting
11. Exporting Back
12. Integration Examples
13. CSV Template

### FAQ.md (Q&A)
1. Getting Started (6 Q&A)
2. Data & Import (9 Q&A)
3. Visualization (6 Q&A)
4. 3D View (6 Q&A)
5. Slideshows & Presentation (7 Q&A)
6. Vignette Effect (4 Q&A)
7. Exporting & Publishing (9 Q&A)
8. Technical (5 Q&A)
9. Troubleshooting (8 Q&A)
10. Getting Help (3 Q&A)

---

## Screenshots

The `screenshots/` directory should contain:

| Screenshot | Shows |
|------------|-------|
| `app-interface.png` | Main timeline view with sample data |
| `data-table.png` | Data tab with event table |
| `import-dialog.png` | CSV import dialog |
| `3d-view.png` | 3D perspective timeline |
| `slideshow-controls.png` | Stops tab and playback controls |
| `vignette-controls.png` | Vignette effect settings |
| `export-dialog.png` | Export options (PNG, MP4, web) |
| `published-page.png` | Web-published timeline in browser |

**Screenshot Guidelines**:
- 1280×720 or 1920×1080 resolution (landscape)
- Show relevant UI elements and features
- Include annotations/callouts for clarity
- Use sample data (not sensitive information)

---

## Contributing to Docs

See [CONTRIBUTING.md - Documentation](../CONTRIBUTING.md#documentation) for how to:
- Fix typos or unclear explanations
- Add examples to clarify features
- Write tutorials for common workflows
- Improve organization of docs

---

**Happy learning!** 📚✨

For the latest updates, see [CHANGELOG.md](../CHANGELOG.md).
