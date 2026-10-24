# Timeline Publisher User Manual

Complete guide to creating, editing, and publishing beautiful timelines with Timeline Publisher.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Creating Your First Timeline](#creating-your-first-timeline)
3. [Importing Data](#importing-data)
4. [Data Management](#data-management)
5. [Timeline Visualization](#timeline-visualization)
6. [3D View](#3d-view)
7. [Styling & Appearance](#styling--appearance)
8. [Creating Slideshows](#creating-slideshows)
9. [Vignette Effect](#vignette-effect)
10. [Exporting & Publishing](#exporting--publishing)
11. [Menu Reference](#menu-reference)

---

## Getting Started

### Launching the App

**macOS**: Double-click "Timeline Publisher" from Applications folder, or use Spotlight (⌘ Space and type "Timeline")

**Web**: Open `Timeline Publisher.html` in any modern browser

### The Main Interface

*Screenshot: Main timeline interface with sample data*

The Timeline Publisher interface contains:

- **Timeline Canvas** (center): Interactive visualization of events over time
- **Side Panel** (right): Tabs for Data, View, Styles, Stops, Export, and File
- **Toolbar** (bottom): Zoom controls and current view info
- **Menu Bar** (top, macOS only): File, Edit, View, and Slideshow menus

### Understanding Tracks

*Screenshot: Timeline with multiple color-coded tracks*

**Tracks** organize events by category. Each track:
- Has a unique color
- Contains multiple events
- Can be shown or hidden
- Maintains its own style settings

Example track structure:
- "Personal" (blue) — Life events
- "Career" (green) — Job milestones
- "Education" (purple) — School achievements

---

## Creating Your First Timeline

### Option 1: Start Blank

1. **Open Timeline Publisher**
2. Choose **File › New Timeline** (or click the New button)
3. You'll see an empty timeline canvas

### Option 2: Load Sample Data

Timeline Publisher includes sample data to explore:

1. Choose **File › Load Sample Story**
2. The "Whitfields" family timeline appears with multiple tracks
3. Explore the interface with real data

### Understanding the Sample Data

*Screenshot: Sample data timeline with "The Whitfields" story*

The sample includes:
- Multiple family members as tracks
- Events spanning decades
- Pre-configured stops for slideshow
- Styling and customization examples

Use this to explore features before importing your own data.

---

## Importing Data

### Preparing Your Data

Create a spreadsheet with these columns:

| Column | Description | Example |
|--------|-------------|---------|
| **Title** | Event name | "Graduated High School" |
| **Start Date** | When event begins | "2020-06-15" or "2020-06" or "2020" |
| **End Date** | When event ends (optional) | "2020-08-31" |
| **Description** | Event details | "Top of class, scholarship awarded" |
| **Track** | Category (optional) | "Education" |

**Date Formats Supported**:
- `YYYY-MM-DD` (2020-06-15) — Most precise
- `YYYY-MM` (2020-06) — Month and year
- `YYYY` (2020) — Year only
- `YYYY-MM-DDTHH:MM:SSZ` (ISO 8601) — With time

Save as `.csv` or `.xlsx` (convert to CSV in Excel if needed).

### Importing a CSV File

*Screenshot: CSV import dialog*

1. Choose **File › Import CSV…**
2. Select your CSV file
3. Choose which track the data belongs to (or create a new one)
4. Select import mode:
   - **Add to existing data**: Combine with current events
   - **Replace all data**: Clear and start fresh
5. Click **Import**

The timeline updates automatically with your data.

### Example CSV

```csv
Title,Start Date,End Date,Description,Track
Joined company,2018-01-15,,Got first full-time job,Career
Led project,2019-06,2019-09,Managed team of 5,Career
Promoted,2020-03,,Became senior engineer,Career
Started MBA,2021-09,2023-05,Evening classes,Education
```

Import this and you'll have a Career and Education track with overlapping events.

---

## Data Management

### The Data Tab

*Screenshot: Data tab showing event table*

The **Data tab** (View › Side Panel › Data) shows all events in table format:

- Each row is one event
- Click to edit any field
- Drag rows to reorder
- Right-click for options

### Editing Events

**In the Table**:
1. Click any cell to edit
2. Type new value
3. Press Enter to save
4. Timeline updates in real-time

**In the Timeline**:
1. Double-click an event card
2. Edit the popup that appears
3. Click outside to save

### Adding Events

1. Go to **Data tab**
2. Click **+ Add Event** at the bottom
3. Fill in Title, Start Date, End Date (optional), Description, Track
4. Press Enter to save

### Deleting Events

1. Right-click an event in the Data table
2. Choose **Delete**
3. Or select and press Delete key

### Track Management

*Screenshot: Track colors and visibility in Data tab*

**View Tracks**:
- Each track appears as a color-coded section
- Toggle visibility with the eye icon
- Click track name to select all its events

**Edit Track Properties**:
1. Data tab › Click track name
2. Edit color, name, or visibility
3. Changes apply immediately

**Hide a Track**:
- Click the eye icon next to track name
- The track's events disappear from timeline
- Stops linked to that track are skipped (see Slideshows section)

---

## Timeline Visualization

### Navigating the Timeline

*Screenshot: Timeline with pan and zoom controls*

**Pan (Move Left/Right)**:
- Click and drag on timeline
- Or use arrow keys (← / →)
- Scrollwheel scrolls horizontally

**Zoom In/Out**:
- Use **View › Zoom In** / **Zoom Out** (⌘= / ⌘-)
- Or **View › Fit All** (⌘0) to see everything
- Scrollwheel with Option key zooms
- Pinch on trackpad zooms

**Focus on Period**:
1. Drag to select a date range
2. Timeline zooms to that period
3. Use Fit All to zoom out again

### Understanding the Timeline Display

- **Horizontal axis**: Time (left = earlier, right = more recent)
- **Vertical stacking**: One track per row
- **Event length**: Shows duration (Start to End Date)
- **Color**: Indicates which track the event belongs to

### Event Cards

*Screenshot: Event card with title, date, and description*

When you hover over or click an event:
- **Title** appears prominently
- **Date range** shown (Start - End)
- **Description** in smaller text
- **Track color** background

### View Controls

The View tab offers:

- **Timeline pan and zoom buttons**
- **Reset to default view**
- **Grid toggle** (shows date markers)
- **Label display options**

---

## 3D View

### Enabling 3D

*Screenshot: 3D timeline view with tilted perspective*

**Toggle 3D Mode**:
- Use **Slideshow › 3D View On/Off** (⌘⇧3)
- Or click 3D button in Stops tab
- Timeline tilts to show perspective depth

### 3D Camera Controls

*Screenshot: 3D view with camera controls visible*

The 3D View section (Stops tab) contains sliders for:

- **Tilt** (0–90°): Angle of perspective, 0 = straight on, 90 = top-down
- **Turn** (0–360°): Rotate left/right around center
- **Zoom** (0.1–10): Magnification level
- **Focus** (0–1): Which layer is in sharp focus
- **Depth** (0–1): 3D depth effect intensity

**Quick Tips**:
- Start at Tilt = 40°, Turn = 0° for good perspective
- Adjust Focus to emphasize certain events
- Use Depth to exaggerate or minimize 3D effect

### 3D Visual Quality

**WebGL Support** (fast, beautiful):
- If your Mac supports WebGL, the 3D view is fully 3D rendered
- Smooth, real-time updates
- Perspective-correct perspective

**Canvas Fallback** (still nice):
- If WebGL isn't available, the app uses canvas 3D
- Slightly less smooth but still functional
- A message appears: "3D rendering (Canvas mode)"

### 3D Labels

*Screenshot: 3D view with event labels positioned above timeline*

In 3D mode, event labels:
- Float above the timeline surface
- Render upright (not tilted) for readability
- Scale based on distance from camera
- Avoid overlapping with collision detection

**Toggle 3D Labels**:
- Checkbox in Stops tab › "Show labels in 3D"
- Useful for cleaner views when labels clutter the display

---

## Styling & Appearance

### The View Tab

*Screenshot: View tab with styling controls*

Use the **View tab** to customize appearance:

- **Track colors**: Click color swatch next to track name
- **Text size**: Global font size adjustment
- **Background**: Image, solid color, or transparent
- **Theme**: Light or dark mode

### Track Colors

*Screenshot: Color picker showing various color options*

**Change Track Color**:
1. Go to **View tab**
2. Click the color swatch next to the track name
3. Choose from preset colors or pick custom
4. Updates timeline immediately

Suggested color schemes:
- Pastel: Soft, modern appearance
- Vivid: High contrast, energetic
- Grayscale: Professional, print-friendly

### Background Image

*Screenshot: Timeline with background image behind events*

**Add Background Image**:
1. View tab › **Background** section
2. Click **+ Add Image**
3. Select image file (JPG, PNG, etc.)
4. Choose display mode:
   - **Fill**: Image fills entire timeline, may crop
   - **Fit**: Entire image visible, may have empty space
5. Adjust opacity if needed

**Remove Background**:
- Click **Remove**

### Theme

*Screenshot: Light theme and dark theme comparison*

**Light Theme**: White/light backgrounds, dark text
**Dark Theme**: Dark background, light text

**Toggle Theme**:
- Use **View › Light / Dark** (⌘⇧L)
- Or click theme button
- All UI updates instantly

### Font Size

*Screenshot: Timeline with different text sizes*

Adjust **Text Size** slider to:
- Make labels more readable
- Fit more events on screen
- Match presentation needs

---

## Creating Slideshows

### Understanding Stops

*Screenshot: Stops tab showing list of stops*

A **Stop** is a snapshot of the timeline in a particular state:
- Specific zoom level and position
- Custom title for the stop
- Configured duration (how long to display)
- Hold time (pause before moving to next stop)

Use stops to guide viewers through your story.

### Adding Stops

*Screenshot: Timeline with "Add Stop" button visible*

**Create a Stop from Current View**:
1. Pan/zoom the timeline to show what you want
2. Go to **Stops tab**
3. Click **+ Add Stop**
4. Give it a title (e.g., "Year 2020", "Career Change")
5. Click **Save**

Or use keyboard: **⌘⇧S**

### Stop Timing

*Screenshot: Stop duration controls*

Each stop has:

- **Title**: What to call this stop
- **Duration (Dur)**: Seconds to display stop (1–30)
- **Hold**: Seconds to pause before transitioning (0–10)

**Example Timing**:
- Dur: 3s, Hold: 1s = show for 3 seconds, then wait 1 second before moving to next stop
- Dur: 5s, Hold: 0s = display continuously, no pause
- Dur: 0s, Hold: 5s = skip over (used for track-linked stops that are hidden)

### Stop Order

*Screenshot: Dragging to reorder stops*

**Reorder Stops**:
1. Stops tab › list of stops
2. Drag stops up/down to reorder
3. Slideshow will follow new order

### Track-Linked Stops

*Screenshot: Stop marked as "Skipped" due to hidden track*

Some stops are tied to specific tracks. When you:
- Hide a track (click eye icon in Data tab)
- Any stops from that track show as "Skipped"
- The slideshow continues, skipping those stops

Use this to create slideshows that adapt to visible tracks.

### Playing the Slideshow

*Screenshot: Slideshow playing with Play/Pause controls*

**Start Slideshow**:
1. Go to **Stops tab**
2. Click **▶ Play** button
3. Or use **Slideshow › Play / Pause** (⌘↩)

**Controls While Playing**:
- **Pause**: Same button toggles pause/play
- **Next Stop**: **Slideshow › Next Stop** (⌘])
- **Previous Stop**: **Slideshow › Previous Stop** (⌘[)
- **Exit**: Press Escape

**Full-Screen Presentation**:
- Click **Present** button, or use **Slideshow › Present Full Screen** (⌘⇧↩)
- Timeline fills entire screen
- Same playback controls
- Press Escape to exit

---

## Vignette Effect

### What is Vignette?

*Screenshot: Timeline with vignette darkening edges*

The **Vignette effect** darkens the edges of your timeline, drawing focus to the center. Useful for presentations and exported videos.

### Vignette Controls

*Screenshot: Vignette controls panel with all sliders*

Go to **Stops tab** › **Vignette** section:

**On / Off**: Toggle vignette visibility

**Amount** (0–100%):
- How dark the edges become
- 0% = no darkening
- 100% = very dark edges
- Typical: 50–70%

**Size** (5–100%):
- How much of center stays clear
- 5% = small clear circle in middle
- 100% = edges barely dark
- Typical: 50–70%

**Softness** (0–100%):
- How gradual the fade is
- 0% = sharp edge between clear and dark
- 100% = very smooth gradient
- Typical: 50–80%

**Roundness** (0–100%):
- Shape of vignette
- 0% = rectangular/frame shape
- 100% = circular
- Typical: 30–50%

**Color**: Choose vignette color
- **Black**: Classic dark vignette
- **Sepia**: Warm, vintage feel
- **White**: Reverse vignette (lightens edges)
- **Custom**: Click to pick any color

### Vignette in Exports

*Screenshot: Exported video frame with vignette applied*

**Include in Videos**: Checkbox determines if vignette is included when exporting MP4 or PNG

- Checked: Vignette applies to all exports
- Unchecked: Exports are unaffected by vignette

### Vignette Tips

- Use moderate amounts (30–50%) for subtle effect
- Increase softness for presentations
- High roundness works well for circular layouts
- Test in slideshow before exporting

---

## Exporting & Publishing

### PNG Frame Export

*Screenshot: Export PNG dialog with options*

**Save Current Frame as PNG**:
1. Position timeline as desired
2. Choose **File › Save Frame as PNG…** (⌘⇧E)
3. Choose save location
4. Set resolution (1280×720, 1920×1080, etc.)
5. Click **Save**
6. PNG file saved to your Downloads folder

**What's Included**:
- Current timeline view
- All visible events
- Vignette effect (if enabled and "Include in exports" is checked)
- Background image (if set)

### MP4 Video Export

*Screenshot: Export MP4 dialog*

**Export as Video**:
1. Go to **Stops tab**
2. Configure stops (duration, timing)
3. Choose **File › Export MP4 Video…** (⌘E)
4. Set options:
   - **Resolution**: 720p, 1080p, 4K
   - **Frame Rate**: 24fps (cinematic), 30fps (standard), 60fps (smooth)
5. Click **Export**
6. Video renders (this may take a few minutes)
7. Saved to your Downloads folder

**What's in the Video**:
- Smooth transitions between stops
- Duration and hold timing applied
- Vignette effect (if enabled and checked)
- All visible events and styling
- Fully self-contained file (no dependencies)

**Performance Notes**:
- 720p at 24fps exports quickly
- 1080p at 60fps takes longer (normal)
- Leave the app in focus while exporting
- Don't close the window until export completes

### CSV Export

*Screenshot: CSV data export*

**Download Data as CSV**:
1. Go to any tab
2. Choose **File › Download CSV…**
3. CSV file contains all your events
4. Useful for backup or importing into other tools

### Web Publishing

*Screenshot: Published HTML page in browser*

**Publish as Web Page**:
1. Configure your stops and styling
2. Choose **File › Publish Web Page…** (⌘⇧P)
3. Choose save location
4. Single HTML file created (no dependencies)
5. Share the `.html` file with others

**Viewing Published Pages**:
- Open in any web browser
- Read-only (viewers can't edit)
- Interactive pan/zoom of timeline
- Playable slideshow with all stops
- No internet connection needed
- Works perfectly on phones and tablets

**What's Shared**:
- Entire timeline and all data
- All styling and colors
- Background image (embedded)
- Configured stops and timing
- No server required

---

## Menu Reference

### File Menu

| Command | Shortcut | Description |
|---------|----------|-------------|
| New Timeline | ⌘N | Create empty timeline |
| Open Project | ⌘O | Load saved `.json` project |
| Import CSV | ⌘⇧O | Import data from CSV file |
| Add Images | ⌘⇧I | Add images to background |
| Save Project | ⌘S | Save current timeline as `.json` |
| Download CSV | — | Export data as CSV |
| Export MP4 | ⌘E | Render video |
| Save Frame as PNG | ⌘⇧E | Export current view as image |
| Publish Web Page | ⌘⇧P | Create shareable HTML |
| Load Sample Story | — | Load example timeline |

### Edit Menu

| Command | Shortcut | Description |
|---------|----------|-------------|
| Undo | ⌘Z | Undo last change |
| Redo | ⌘⇧Z | Redo last undo |
| Cut | ⌘X | Cut selected text |
| Copy | ⌘C | Copy selected text |
| Paste | ⌘V | Paste from clipboard |
| Paste & Match Style | ⌘⌃V | Paste without formatting |
| Select All | ⌘A | Select all text |
| Edit Data Table | ⌘⇧D | Show/hide data table editor |

### View Menu

| Command | Shortcut | Description |
|---------|----------|-------------|
| Zoom In | ⌘= | Magnify timeline |
| Zoom Out | ⌘- | Reduce magnification |
| Fit All | ⌘0 | Show entire timeline |
| Toggle Side Panel | ⌘\ | Show/hide right panel |
| Side Panel › Data | ⌘1 | Show Data tab |
| Side Panel › View | ⌘2 | Show View tab |
| Side Panel › Styles | ⌘3 | Show Styles tab |
| Side Panel › Stops | ⌘4 | Show Stops tab |
| Side Panel › Export | ⌘5 | Show Export tab |
| Side Panel › File | ⌘6 | Show File tab |
| Light / Dark | ⌘⇧L | Toggle theme |
| Full Screen | ⌘⌃F | Enter full-screen mode |

### Slideshow Menu

| Command | Shortcut | Description |
|---------|----------|-------------|
| Play / Pause | ⌘↩ | Start or pause slideshow |
| Present Full Screen | ⌘⇧↩ | Start full-screen presentation |
| Next Stop | ⌘] | Jump to next stop |
| Previous Stop | ⌘[ | Jump to previous stop |
| Add Stop | ⌘⇧S | Create new stop |
| 3D View On / Off | ⌘⇧3 | Toggle 3D perspective |
| Vignette On / Off | ⌘⇧V | Toggle edge darkening |

---

## Tips & Tricks

### Data Organization

- **Use tracks effectively**: Different colored tracks make it easy to distinguish categories
- **Consistent naming**: Use similar date formats and title styles
- **Meaningful descriptions**: Good descriptions make events memorable when presenting

### Timeline Navigation

- **Zoom before creating stops**: Set up the exact view you want, then create a stop
- **Use Fit All to reset**: Lost? Press ⌘0 to zoom back to see everything
- **Pan with keyboard**: Arrow keys let you scroll hands-free

### Presentations

- **Test full-screen first**: Try **Slideshow › Present Full Screen** before the actual presentation
- **Use vignette subtly**: 40–50% Amount with 60% Size looks professional
- **Configure timing**: Test stop durations to match your narration pace
- **Show track visibility strategically**: Hide/show tracks to focus on relevant storylines

### Exports

- **PNG for printing**: 1920×1080 resolution good for 11×6 inch prints
- **MP4 for sharing**: 1080p at 30fps balances quality and file size
- **CSV backup**: Always export data before major changes
- **Web publish for mobile**: Published HTML works great on phones/tablets

### Performance

- **Large timelines**: 1000+ events may slow down slightly (normal)
- **3D on older Macs**: Turn off 3D or reduce 3D Depth if performance is sluggish
- **Video export**: Rendering takes time (especially high resolution). Leave app running until complete

---

## Keyboard Shortcut Summary

| Action | macOS | Web |
|--------|-------|-----|
| New | ⌘N | — |
| Open | ⌘O | — |
| Save | ⌘S | — |
| Undo | ⌘Z | ⌘Z |
| Redo | ⌘⇧Z | ⌘⇧Z |
| Zoom In | ⌘= | ⌘= |
| Zoom Out | ⌘- | ⌘- |
| Fit All | ⌘0 | ⌘0 |
| Play Slideshow | ⌘↩ | ⌘↩ |
| Full Screen | ⌘⇧↩ | F |
| Next Stop | ⌘] | ⌘] |
| Previous Stop | ⌘[ | ⌘[ |
| Add Stop | ⌘⇧S | ⌘⇧S |
| Toggle 3D | ⌘⇧3 | ⌘⇧3 |
| Toggle Vignette | ⌘⇧V | ⌘⇧V |

---

## Troubleshooting

### Common Issues

**Events don't appear after import**
- Check that Date columns are properly formatted (YYYY-MM-DD recommended)
- Ensure Track column matches an existing track (or create new track with correct name)
- Try importing with "Replace all data" mode first

**3D view is blank or black**
- This may mean WebGL isn't available on your system
- The app falls back to canvas mode automatically
- Try toggling 3D off and on again

**Video export is slow**
- High resolution + high FPS = longer export times
- Try 1080p at 24fps first to speed up
- Don't switch apps while exporting (let it complete)

**App crashes on startup**
- Delete the app and reinstall fresh version
- On Mac, move the app from Applications to Trash, then download again

**Can't find the saved file**
- Check your Downloads folder (default save location)
- Use **File › [Export type]**, which shows the file location when done
- Spotlight search (⌘ Space) for the filename

---

## Getting Help

- **Questions?** Open an issue on [GitHub](https://github.com/dougalder/timeline-publisher)
- **Found a bug?** Report it with steps to reproduce
- **Feature request?** Let us know what you'd like to see

---

**Happy storytelling!** 🎬📊✨
