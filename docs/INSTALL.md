# Installation Guide

Guide to installing Timeline Publisher for different platforms and use cases.

## macOS Desktop App

### System Requirements
- macOS 10.13 (High Sierra) or later
- Apple Silicon (M1/M2/M3) or Intel processor
- 50 MB disk space
- No internet connection required

### Installation Steps

1. **Download**: Go to [Releases](https://github.com/dougalder/timeline-publisher/releases) and download the latest `.dmg` file
2. **Mount**: Double-click the `.dmg` file
3. **Install**: Drag "Timeline Publisher" to the Applications folder
4. **Launch**: 
   - Open Applications folder
   - Double-click "Timeline Publisher"
   - Or use Spotlight: ⌘ Space, type "Timeline", press Enter

### First Launch

On first launch, macOS may show a security warning:
- Click **Open** to proceed
- This is normal for apps from outside the App Store
- The warning won't appear again

### File Associations

After installation, double-clicking these file types opens them in Timeline Publisher:
- `.json` — Timeline Publisher projects
- `.csv` — Spreadsheet data files
- `.tsv` — Tab-separated data
- `.txt` — Text data files

### Updating

When a new version is released:
1. Download the latest `.dmg`
2. Drag the new "Timeline Publisher" to Applications
3. Confirm to replace the old version
4. All your existing projects work with the new version

### Uninstalling

Simply delete the app:
1. Open Applications folder
2. Find "Timeline Publisher"
3. Drag to Trash (or press ⌘ Delete)
4. Projects saved on your Mac remain unchanged

**Config files stored at**: `~/Library/Application Support/Timeline Publisher/` (can be deleted if you want to reset window position)

## Web Version

### Running Locally

The easiest way to use the web version:

1. **Download**: Get `Timeline Publisher.html` from the repository or latest release
2. **Save**: Put the file anywhere on your computer (Downloads, Documents, Desktop, etc.)
3. **Open**: Double-click `Timeline Publisher.html`
4. **Use**: Starts in your default browser

### Browser Compatibility

Works with:
- ✅ **Chrome** / Chromium 60+ (recommended for best 3D)
- ✅ **Safari** 12+
- ✅ **Firefox** 55+
- ✅ **Edge** 79+

Features requiring WebGL (3D visualization):
- Works best in Chrome/Chromium
- Fallback canvas mode on other browsers

### Web from GitHub Pages

To run directly from GitHub without downloading:

1. Visit: https://github.com/dougalder/timeline-publisher/releases
2. Find the latest release
3. Open `Timeline Publisher.html` directly from the release page
4. Browser loads and runs it (read-only mode)

**Note**: Saving projects requires the desktop version (web version can download data but not save to browser storage reliably)

## Building from Source

For developers who want to build Timeline Publisher locally.

### Prerequisites

Install these first:
- **Node.js 18+**: Download from https://nodejs.org/
- **npm** (comes with Node.js)
- **Git**: Download from https://git-scm.com/

Verify installation:
```bash
node --version      # Should be 18 or higher
npm --version       # Should be 8 or higher
git --version       # Should be 2.x
```

### Clone Repository

```bash
git clone https://github.com/dougalder/timeline-publisher.git
cd timeline-publisher
```

### Install Dependencies

```bash
npm install
```

This downloads and installs:
- Electron (44.5.1)
- electron-packager
- playwright-core
- Other dependencies

### Run Web Version

Open `app/index.html` in your browser:
```bash
# macOS
open app/index.html

# Linux
xdg-open app/index.html

# Or just double-click the file in Finder/File Explorer
```

### Run Desktop App

```bash
npm start
```

This launches the app in development mode with the Electron shell.

### Run Tests

```bash
npm test
```

This runs the full end-to-end test suite using Playwright. Tests verify:
- App launches correctly
- Menu commands work
- Data import/export functions
- 3D rendering
- Video export
- All 33 test cases pass

## Building macOS Package

To create a distributable macOS app from source:

### Prerequisites
- macOS 11 or later
- Command line tools: `xcode-select --install`
- Code signing certificate (optional, uses ad-hoc signing)

### Build

```bash
# Build, sign, and package for macOS
bash pack-mac.sh
```

This script:
1. Builds the app with electron-packager
2. Removes unnecessary files to reduce size
3. Ad-hoc code signs (no certificate required)
4. Creates a distributable `.dmg`

The built app appears in: `out/Timeline Publisher-darwin-arm64/`

### Package Size
- Uncompressed: ~150 MB
- `.dmg` compressed: ~80 MB

### Distribution

The `.dmg` file is ready to distribute:
- Place on GitHub Releases
- Host on a website
- Share via email
- Works on any macOS 10.13+ Mac

## Troubleshooting

### "Can't open Timeline Publisher" on macOS

**Problem**: Security warning saying the app is from an unknown developer

**Solution**:
1. Go to System Preferences › Security & Privacy
2. Click "Open Anyway" next to the warning
3. The app launches and won't warn again

Or from command line:
```bash
xattr -d com.apple.quarantine "~/Applications/Timeline Publisher.app"
```

### "Module not found" when running from source

**Problem**: `npm install` incomplete or cached

**Solution**:
```bash
rm -rf node_modules package-lock.json
npm install
```

### Tests fail when building

**Problem**: Playwright browser download or test environment issue

**Solution**:
```bash
npm test -- --headed    # Run tests in headed mode (see what's happening)
```

Or rebuild:
```bash
npm install --save playwright-core
```

### Web version slow on some browsers

**Problem**: 3D rendering slow on Safari or Firefox

**Solution**:
- WebGL isn't available, so canvas fallback is used
- Still functional, just slightly slower
- Try in Chrome for best 3D performance

### Can't save files in web version

**Problem**: Browser security prevents downloads

**Solution**:
- Use the desktop app for reliable saving
- Or in web version, export as CSV which works in all browsers
- Publish as web page to share timelines

---

## Docker / Container Deployment

For running Timeline Publisher in Docker:

```dockerfile
FROM node:18-alpine

WORKDIR /app
COPY . .

RUN npm install

EXPOSE 8000

# For web version only (no Electron)
CMD ["python3", "-m", "http.server", "8000"]
```

Build and run:
```bash
docker build -t timeline-publisher .
docker run -p 8000:8000 timeline-publisher
```

Then visit: http://localhost:8000/app/index.html

**Note**: Docker running is for the web version only. The desktop app requires macOS/native environment.

---

## Deployment to Website

To host the web version on your own website:

1. Copy `app/index.html` to your web server
2. Ensure the server supports UTF-8 and HTML5
3. Access via: `https://yoursite.com/timeline-publisher.html`

No server-side processing needed—it's pure HTML5 and JavaScript.

---

## Next Steps

After installation:
1. **Quick start**: [MANUAL.md](MANUAL.md) — Getting started guide
2. **Data format**: [CSV-FORMAT.md](CSV-FORMAT.md) — How to prepare data
3. **Keyboard shortcuts**: [KEYBOARD-SHORTCUTS.md](KEYBOARD-SHORTCUTS.md) — All shortcuts
4. **FAQs**: [FAQ.md](FAQ.md) — Answers to common questions

Happy storytelling! 📊✨
