# Directory Structure

Complete layout of the Timeline Publisher repository.

```
timeline-publisher/
├── README.md                      # Project overview and quick start
├── LICENSE                        # MIT License
├── CHANGELOG.md                   # Version history and features
├── CONTRIBUTING.md                # Guidelines for contributors
├── .gitignore                     # Git ignore rules
│
├── docs/                          # Documentation
│   ├── MANUAL.md                 # Complete user guide with screenshots
│   ├── INSTALL.md                # Installation and setup
│   ├── KEYBOARD-SHORTCUTS.md      # All keyboard shortcuts
│   ├── CSV-FORMAT.md              # Data import format guide
│   ├── FAQ.md                     # Frequently asked questions
│   └── screenshots/               # Screenshot images for docs
│       ├── app-interface.png
│       ├── data-table.png
│       ├── 3d-view.png
│       └── ...more screenshots
│
├── app/                           # Web application
│   ├── index.html                # Main application (all UI + JS)
│   └── sample-data.json          # Sample timeline for demos
│
├── build/                         # Build assets
│   └── icon.icns                 # macOS app icon
│
├── tests/                         # Testing
│   ├── e2e.mjs                   # End-to-end tests (Playwright)
│   └── run.sh                    # Test runner script
│
├── .github/                       # GitHub configuration
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md         # Bug report template
│   │   └── feature_request.md    # Feature request template
│   └── workflows/
│       └── tests.yml             # CI/CD workflow
│
├── main.js                        # Electron main process
├── preload.js                     # Electron preload script
├── build.mjs                      # Build script
├── pack-mac.sh                    # macOS packaging script
│
├── package.json                   # Node dependencies and scripts
├── package-lock.json              # Locked dependency versions
│
└── out/                           # Built app (generated)
    └── Timeline Publisher-darwin-arm64/  # Packaged macOS app
        └── Timeline Publisher.app
```

## File Descriptions

### Root Level

| File | Purpose |
|------|---------|
| `README.md` | Project overview, features, quick start, links to docs |
| `LICENSE` | MIT open source license |
| `CHANGELOG.md` | Version history, features added, bugs fixed |
| `CONTRIBUTING.md` | Guidelines for contributors, how to build from source |
| `.gitignore` | Files to exclude from git (node_modules, build artifacts, etc.) |
| `DIRECTORY_STRUCTURE.md` | This file—layout and file descriptions |

### App Directory (`app/`)

| File | Purpose |
|------|---------|
| `index.html` | **Complete web application**—contains all UI, styling, and JavaScript. Loaded by the macOS Electron app and opened directly in browsers for the web version. |
| `sample-data.json` | Sample timeline ("The Whitfields") used by File › Load Sample Story |

### Build Directory (`build/`)

| File | Purpose |
|------|---------|
| `icon.icns` | App icon for macOS (includes 16x16 through 1024x1024 resolutions) |

### Docs Directory (`docs/`)

Complete user documentation:

| File | Purpose |
|------|---------|
| `MANUAL.md` | **Main user guide**—detailed walkthroughs of all features with screenshots. Includes data import, timeline visualization, 3D view, slideshows, vignette effects, exporting, publishing. |
| `INSTALL.md` | Installation for macOS app, web version, building from source |
| `KEYBOARD-SHORTCUTS.md` | Complete keyboard shortcut reference for macOS and web versions |
| `CSV-FORMAT.md` | How to prepare spreadsheet data for import—date formats, column definitions, examples |
| `FAQ.md` | Answers to 50+ frequently asked questions organized by topic |
| `screenshots/` | Screenshot images used in documentation (user adds these after initial setup) |

### Tests Directory (`tests/`)

| File | Purpose |
|------|---------|
| `e2e.mjs` | **End-to-end tests**—33 comprehensive Playwright tests covering all major features (import, editing, 3D, export, etc.) |
| `run.sh` | Test runner script—sets up virtual display and runs tests |

### GitHub Directory (`.github/`)

GitHub-specific configuration:

```
.github/
├── ISSUE_TEMPLATE/
│   ├── bug_report.md       # Bug report template
│   └── feature_request.md  # Feature request template
└── workflows/
    └── tests.yml           # GitHub Actions CI/CD
```

### Electron App Files

| File | Purpose |
|------|---------|
| `main.js` | **Electron main process**—handles window creation, menu bar, file dialogs, IPC bridge |
| `preload.js` | **Security bridge**—exposes limited functionality to web page (reveal files, platform info) |
| `build.mjs` | **Build script**—uses electron-packager to create distributable app |
| `pack-mac.sh` | **Packaging script**—calls build.mjs, signs app, creates .dmg |

### Node/NPM Files

| File | Purpose |
|------|---------|
| `package.json` | Project metadata, dependencies (electron, playwright-core), build scripts |
| `package-lock.json` | Locked versions of all dependencies (created by npm) |

### Output Directory (`out/`)

Generated during build—contains the packaged macOS app:

```
out/
└── Timeline Publisher-darwin-arm64/
    ├── Timeline Publisher.app/
    │   └── Contents/
    │       ├── MacOS/
    │       ├── Resources/
    │       │   └── app/
    │       │       └── index.html
    │       └── Info.plist
    └── Timeline Publisher.dmg
```

## How Files Work Together

### Web Version Flow

1. **User opens** `app/index.html` in browser
2. **Browser loads** HTML, CSS, and JavaScript
3. **JavaScript runs** all app logic in browser
4. **User can** create, edit, export timelines
5. **Exports saved** to Downloads (browser downloads)

### Desktop App Flow

1. **Electron** (main.js) creates window
2. **Window loads** `app/index.html` inside Electron shell
3. **Preload.js** provides security bridge
4. **User interface** same as web, but with menu bar + file dialogs
5. **File operations** handled by Electron (native save dialogs, reveal in Finder)

### Build Flow

```
Development:
  npm install          → Install dependencies
  npm start            → Run Electron app in dev mode
  npm test             → Run tests

Release:
  bash pack-mac.sh     → Build and package
    ↓ (calls build.mjs)
  electron-packager    → Creates macOS app
    ↓
  Ad-hoc signing       → Signs the app
    ↓
  Create .dmg          → Distributable installer
    ↓
  Release upload       → GitHub releases page
```

## Key Design Decisions

### Why is app/index.html one large file?

- **Portability**: Works as web version and in Electron without changes
- **No dependencies**: Zero NPM packages at runtime (only Electron)
- **Self-contained**: Includes all CSS, JavaScript, no external script loading
- **Simplicity**: Single file easier to understand and modify

### Why separate main.js, preload.js, index.html?

- **Security**: Preload creates minimal bridge between untrusted page and native APIs
- **Separation of concerns**: Electron shell vs web app logic stay separate
- **Flexibility**: Same app.html works in both browser and Electron

### Why Playwright for tests instead of Jest/Mocha?

- **End-to-end**: Tests the actual Electron app, not mocked components
- **Visual verification**: Can capture screenshots and verify rendering
- **File I/O**: Tests real file operations (import, export, saving)
- **Multiple environments**: Same tests run on web and desktop

---

## Adding to This Repository

### Adding Documentation

1. Create file in `docs/` directory
2. Link from `README.md` and other relevant docs
3. Update this `DIRECTORY_STRUCTURE.md` if adding new category

### Adding Features

1. Edit `app/index.html` (add UI, styling, JavaScript)
2. Add tests to `tests/e2e.mjs`
3. Update `MANUAL.md` with feature description
4. Update `CHANGELOG.md` with "Unreleased" section

### Adding Screenshots

1. Create folder: `docs/screenshots/`
2. Add screenshots: `docs/screenshots/feature-name.png`
3. Reference in docs: `![Description](docs/screenshots/feature-name.png)`
4. Aim for 1280×720 or similar landscape ratio

---

See [CONTRIBUTING.md](CONTRIBUTING.md) for development guidelines and [INSTALL.md](docs/INSTALL.md) for building from source.
