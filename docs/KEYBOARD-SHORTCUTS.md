# Keyboard Shortcuts

Complete reference for all keyboard shortcuts in Timeline Publisher.

## macOS Shortcuts

### File Operations

| Shortcut | Command | Description |
|----------|---------|-------------|
| ⌘N | New Timeline | Create a new empty timeline |
| ⌘O | Open Project | Open a saved `.json` project file |
| ⌘S | Save Project | Save current timeline as `.json` |
| ⌘⇧O | Import CSV | Import data from CSV file |
| ⌘⇧I | Add Images | Add background image |
| ⌘E | Export MP4 | Export timeline as video |
| ⌘⇧E | Save PNG | Save current frame as image |
| ⌘⇧P | Publish | Create shareable HTML page |

### Editing

| Shortcut | Command | Description |
|----------|---------|-------------|
| ⌘Z | Undo | Undo last change |
| ⌘⇧Z | Redo | Redo last undo |
| ⌘X | Cut | Cut selected text |
| ⌘C | Copy | Copy selected text |
| ⌘V | Paste | Paste from clipboard |
| ⌘⌃V | Paste Style | Paste without formatting |
| ⌘A | Select All | Select all text |
| ⌘⇧D | Edit Table | Show/hide data table editor |

### View & Navigation

| Shortcut | Command | Description |
|----------|---------|-------------|
| ⌘= | Zoom In | Magnify the timeline |
| ⌘- | Zoom Out | Reduce magnification |
| ⌘0 | Fit All | Show entire timeline (reset zoom) |
| ⌘\ | Toggle Panel | Show/hide right side panel |
| ← | Pan Left | Move timeline left |
| → | Pan Right | Move timeline right |
| ⌘⇧L | Light/Dark | Toggle dark/light theme |
| ⌘⌃F | Full Screen | Enter full-screen mode |

### Sidebar Tabs

| Shortcut | Tab | Description |
|----------|-----|-------------|
| ⌘1 | Data | Show data table editor |
| ⌘2 | View | Show view/styling controls |
| ⌘3 | Styles | Show style options |
| ⌘4 | Stops | Show slideshow stops |
| ⌘5 | Export | Show export options |
| ⌘6 | File | Show file/info |

### Slideshow & Presentation

| Shortcut | Command | Description |
|----------|---------|-------------|
| ⌘↩ | Play / Pause | Start or pause slideshow |
| ⌘⇧↩ | Full Screen | Start full-screen presentation |
| ⌘] | Next Stop | Jump to next stop in slideshow |
| ⌘[ | Previous Stop | Jump to previous stop |
| ⌘⇧S | Add Stop | Create new stop from current view |
| ⌘⇧3 | Toggle 3D | Switch 3D perspective on/off |
| ⌘⇧V | Toggle Vignette | Switch vignette effect on/off |
| Escape | Exit | Exit slideshow or full-screen |

## Web Version Shortcuts

The web version supports most shortcuts (without ⌘ where macOS app uses it):

### View Control

| Shortcut | Command |
|----------|---------|
| ⌘= or Ctrl+= | Zoom In |
| ⌘- or Ctrl+- | Zoom Out |
| ⌘0 or Ctrl+0 | Fit All |
| ⌘⇧L or Ctrl⇧L | Light/Dark |
| Arrow Keys | Pan left/right |

### Slideshow

| Shortcut | Command |
|----------|---------|
| ⌘↩ or Ctrl+Enter | Play / Pause |
| ⌘] or Ctrl+] | Next Stop |
| ⌘[ or Ctrl+[ | Previous Stop |
| ⌘⇧S or Ctrl⇧S | Add Stop |
| ⌘⇧3 or Ctrl⇧3 | Toggle 3D |
| ⌘⇧V or Ctrl⇧V | Toggle Vignette |
| F | Full Screen |
| Escape | Exit |

### Editing

| Shortcut | Command |
|----------|---------|
| ⌘Z or Ctrl+Z | Undo |
| ⌘⇧Z or Ctrl⇧Z | Redo |
| ⌘X or Ctrl+X | Cut |
| ⌘C or Ctrl+C | Copy |
| ⌘V or Ctrl+V | Paste |

## Touch & Trackpad Shortcuts

### macOS Trackpad

| Gesture | Action |
|---------|--------|
| Two-finger scroll | Pan timeline |
| Pinch in/out | Zoom in/out |
| Three-finger tap | Double-click |

### Magic Mouse

| Gesture | Action |
|---------|--------|
| One-finger drag | Pan timeline |
| Two-finger scroll | Zoom in/out |

## In-App Keyboard Navigation

### Data Table

| Key | Action |
|-----|--------|
| Tab | Move to next cell |
| Shift+Tab | Move to previous cell |
| Enter | Save current cell, move to next row |
| Delete | Clear cell contents |
| Escape | Cancel edit |
| ↑↓ | Move between rows |

### Timeline

| Key | Action |
|-----|--------|
| ← → | Pan left/right |
| + - | Zoom in/out |
| Space | Play/pause slideshow |
| Escape | Deselect current event |
| Enter | Edit selected event |

## Customizing Shortcuts (macOS App)

The macOS app uses standard Electron/system shortcuts. To customize:

1. **Menu bar shortcuts** are defined in `main.js`
2. **To change**: Edit the accelerator field in the menu template
3. **Example**: Change ⌘E to ⌘⇧E by modifying the menu item

See [Building from Source](INSTALL.md#building-from-source) for how to modify and rebuild.

## Accessibility Shortcuts

### macOS Accessibility

Timeline Publisher supports standard macOS accessibility:

| Shortcut | Feature |
|----------|---------|
| Ctrl+Option+Right | Increase text size |
| Ctrl+Option+Left | Decrease text size |
| Cmd+Option+? | Accessibility help |

### Web Version Accessibility

- Tab through controls using keyboard
- Enter/Space to activate buttons
- Arrow keys in select lists
- Labels and alt text support screen readers

## Reference Card

Print this quick reference for your desk:

```
TIMELINE PUBLISHER — Quick Shortcuts

FILES                     VIEW & ZOOM               SLIDESHOW
⌘N  New Project          ⌘=  Zoom In              ⌘↩   Play/Pause
⌘O  Open Project         ⌘-  Zoom Out             ⌘⇧↩  Full Screen
⌘S  Save Project         ⌘0  Fit All              ⌘]   Next Stop
⌘⇧O Import CSV           ⌘\  Toggle Panel         ⌘[   Previous Stop
⌘E  Export Video         ⌘⇧L Light/Dark           ⌘⇧S  Add Stop
⌘⇧E Save Frame           ⌘⌃F Full Screen         ⌘⇧3  Toggle 3D
⌘⇧P Publish Web          ⌘1-6 Tabs                ⌘⇧V  Toggle Vignette

EDITING                  NAVIGATION
⌘Z  Undo                 ←→  Pan Left/Right
⌘⇧Z Redo                 Tab  Next Field
⌘X  Cut                  Esc  Deselect
⌘C  Copy
⌘V  Paste
⌘⇧D Edit Table
```

---

## Tips for Power Users

### Efficiency

- **Memorize the top 5**: ⌘S (save), ⌘↩ (play), ⌘] (next), ⌘0 (fit), ⌘Z (undo)
- **One-handed zoom**: ⌘= and ⌘- are near the right hand on keyboard
- **Tab switching**: ⌘1-6 for quick access to all panels

### Workflow

1. **Create & Edit**: ⌘⇧D to edit table, ⌘Z to undo mistakes
2. **Navigate**: ⌘0 to reset view, ⌘= to zoom in on details
3. **Slideshow**: ⌘⇧S to add stop, ⌘↩ to test playback
4. **Export**: ⌘⇧E for PNG, ⌘E for video, ⌘⇧P for web

### Speed Editing

- **Quick save**: ⌘S after every important change
- **Undo recovery**: ⌘Z a few times if you make a mistake
- **Zoom to detail**: ⌘= then double-click event to edit
- **Back to overview**: ⌘0 to return to full view

---

**Keyboard mastery = faster storytelling!** 🚀

See [MANUAL.md](MANUAL.md) for detailed feature descriptions.
