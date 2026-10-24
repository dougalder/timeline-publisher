# Frequently Asked Questions

Common questions about Timeline Publisher and how to use it.

## Getting Started

### Q: What do I need to run Timeline Publisher?

**A:** Two options:
- **macOS App**: macOS 10.13+, 50 MB space
- **Web Version**: Any modern browser (Chrome, Safari, Firefox, Edge)

Both work offline—no internet required.

### Q: Is Timeline Publisher free?

**A:** Yes! Timeline Publisher is open source (MIT license). Use it for personal or commercial projects at no cost.

### Q: How do I install it?

**A:** See [Installation Guide](INSTALL.md) for detailed steps. Quick version:
- **macOS**: Download `.dmg` from releases, drag to Applications
- **Web**: Open `Timeline Publisher.html` in your browser

### Q: Can I use it on Windows/Linux?

**A:** The macOS app is macOS only. But the web version works on any computer (Windows, Linux, Mac) in any browser.

## Data & Import

### Q: What date formats does it support?

**A:** All common formats:
- `YYYY-MM-DD` (2020-06-15) ← Recommended
- `YYYY-MM` (2020-06)
- `YYYY` (2020)
- `MM/DD/YYYY` (06/15/2020)
- And more — see [CSV Format Guide](CSV-FORMAT.md)

### Q: Can I import Excel files?

**A:** Not directly, but it's easy:
1. Export Excel to CSV
2. Import CSV into Timeline Publisher

[CSV Format Guide](CSV-FORMAT.md) has detailed instructions.

### Q: How do I organize events into tracks?

**A:** Tracks are categories:
1. Add a "Track" column to your CSV
2. Give events track names (e.g., "Career", "Education", "Family")
3. Import the CSV
4. Events are automatically grouped by track with color coding

### Q: Can I edit events after import?

**A:** Yes! Edit in two ways:
- **Table**: Data tab › click any cell › edit
- **Timeline**: Double-click event card › edit popup

Changes apply in real-time.

### Q: How many events can I have?

**A:** Timeline Publisher handles 1000+ events comfortably. Very large timelines (5000+) may be slower, but still functional.

### Q: Can I delete events?

**A:** Yes:
1. Data tab › right-click event
2. Choose **Delete**
3. Or select and press Delete key

## Visualization

### Q: How do I zoom in and out?

**A:** Multiple ways:
- Menu: **View › Zoom In** / **Zoom Out** (⌘= / ⌘-)
- Buttons: Toolbar zoom controls
- Trackpad: Pinch in/out
- Keyboard: ⌘0 to reset and see all

### Q: What's the difference between pan and zoom?

**A:** 
- **Pan**: Move left/right without changing magnification
- **Zoom**: Change magnification level

Both let you explore the timeline.

### Q: Can I add background images?

**A:** Yes:
1. View tab › **Background** section
2. Click **+ Add Image**
3. Choose JPG or PNG
4. Select **Fill** or **Fit** mode
5. Adjust opacity if needed

### Q: How do I change track colors?

**A:** 
1. View tab
2. Click color swatch next to track name
3. Choose preset color or pick custom
4. Updates instantly

## 3D View

### Q: What is 3D mode?

**A:** A perspective view that tilts the timeline for visual interest. Use **Slideshow › 3D View On/Off** (⌘⇧3) to toggle.

### Q: Why is 3D view slow?

**A:** Three possible reasons:
1. **No WebGL support**: App uses slower canvas mode (still works)
2. **Old Mac**: Older graphics hardware is slower
3. **Large dataset**: 1000+ events may slow down

Try reducing event count or using 2D mode.

### Q: Which browser is best for 3D?

**A:** Chrome/Chromium (best WebGL support). Safari and Firefox work but may be slower. Firefox has a note about canvas fallback being used.

### Q: Can I export videos with 3D?

**A:** Yes! The 3D view exports to MP4/WebM with all perspective effects intact.

## Slideshows & Presentation

### Q: What are "stops"?

**A:** Stops are key moments in your story:
- Specific view of the timeline
- Custom title for each stop
- Configured timing
- Viewers advance through stops in sequence

### Q: How do I create a slideshow?

**A:**
1. Position timeline to show what you want
2. Stops tab › **+ Add Stop**
3. Give it a title
4. Adjust duration and hold time
5. Repeat for each key moment
6. Click **Play** to preview

### Q: How do I set stop timing?

**A:** Each stop has:
- **Duration** (1–30s): How long to display
- **Hold** (0–10s): Pause before moving to next

Example: 3s duration + 1s hold = show for 3s, pause 1s, then advance.

### Q: Can I reorder stops?

**A:** Yes! In Stops tab, drag stops up/down to reorder. Slideshow follows new order.

### Q: What happens when I hide a track?

**A:** Stops from hidden tracks are marked "Skipped" and don't play during slideshow. Perfect for adapting presentations to different audiences.

### Q: Can I present full-screen?

**A:** Yes! Use **Slideshow › Present Full Screen** (⌘⇧↩) or click Present button. Press Escape to exit.

## Vignette Effect

### Q: What does vignette do?

**A:** It darkens the edges of your timeline, creating focus and visual polish. Great for presentations and video exports.

### Q: How do I use vignette?

**A:**
1. Stops tab › **Vignette** section
2. Toggle **On**
3. Adjust:
   - **Amount**: How dark (0–100%)
   - **Size**: How much center stays clear
   - **Softness**: How gradual the fade
   - **Roundness**: Shape (square to circular)
4. Choose color (black, sepia, white, custom)

### Q: Does vignette affect exported videos?

**A:** Only if "Include in videos" is checked. Toggle the checkbox to include/exclude vignette from MP4 and PNG exports.

### Q: What are good vignette settings?

**A:** Recommended starting points:
- **Amount**: 50–60%
- **Size**: 60–70%
- **Softness**: 70–80%
- **Roundness**: 30–50%
- **Color**: Black (classic)

Test and adjust to your preference.

## Exporting & Publishing

### Q: How do I save a project?

**A:** Use **File › Save Project…** (⌘S) to save as `.json` file. This includes:
- All events and tracks
- Stops and timing
- Styling and colors
- Vignette settings

### Q: What's the difference between Save Project and Download CSV?

**A:**
- **Save Project** (`.json`): Everything—styling, stops, 3D settings. For editing later.
- **Download CSV** (`.csv`): Just the events and data. For Excel or sharing data.

### Q: How do I export as PNG?

**A:**
1. Position timeline to show desired frame
2. **File › Save Frame as PNG** (⌘⇧E)
3. Choose resolution (1280×720, 1920×1080, etc.)
4. File saved to Downloads folder

### Q: How long does video export take?

**A:** Depends on settings:
- 720p @ 24fps: ~1–2 minutes
- 1080p @ 30fps: ~3–5 minutes
- 4K @ 60fps: ~15–30 minutes

It's normal for video export to be slow. Leave the app running until complete.

### Q: What video resolution should I use?

**A:** Depends on your need:
- **Social media**: 720p @ 24fps (small file, fast)
- **Presentations**: 1080p @ 30fps (standard)
- **Cinema**: 1080p @ 24fps (cinematic feel)
- **Web**: 720p @ 24fps (balances quality & speed)

### Q: Can I publish to the web?

**A:** Yes! **File › Publish Web Page** (⌘⇧P) creates a single HTML file that:
- Works in any browser
- Is read-only (viewers can't edit)
- Has interactive pan/zoom
- Includes playable slideshow
- Requires no internet

### Q: How do I share published pages?

**A:** Share the `.html` file:
- Email it to someone
- Upload to your website
- Share via cloud storage (Google Drive, Dropbox, etc.)
- Post on social media (some platforms support HTML)

The file is self-contained—no dependencies needed.

## Technical

### Q: Is my data private?

**A:** Yes! Timeline Publisher:
- Works completely offline
- Never sends data to any server
- Stores projects locally on your Mac
- No analytics or tracking

Your timelines stay 100% private.

### Q: Can I edit published HTML files?

**A:** The published files are read-only in the browser. To edit:
1. Keep the original `.json` project file
2. Edit in Timeline Publisher
3. Publish again (replaces old HTML)

### Q: What format are project files?

**A:** Projects are `.json` (JavaScript Object Notation):
- Human-readable text
- Can be opened in any text editor
- Contain all timeline data
- Can be imported to Timeline Publisher again

### Q: Can I use Timeline Publisher in a Docker container?

**A:** The web version yes, the app no. See [Installation Guide](INSTALL.md#docker--container-deployment) for Docker setup.

### Q: Can I integrate Timeline Publisher into my website?

**A:** You can:
- Publish a timeline and host the HTML
- Users open that HTML in their browser
- Read-only view for your audience

For embedding in an existing page, see [Installation Guide](INSTALL.md#deployment-to-website).

## Troubleshooting

### Q: The app won't launch on macOS

**A:** Try:
1. Right-click the app › **Open** (bypasses security warning)
2. Or go to System Preferences › Security & Privacy › Allow
3. Reinstall the latest version

See [Installation Guide](INSTALL.md#troubleshooting) for more solutions.

### Q: My CSV import doesn't work

**A:** Check:
1. File is actually `.csv` (not `.xls` or `.xlsx`)
2. First row has headers (Title, Start Date, etc.)
3. Date format is recognized (see [CSV Format Guide](CSV-FORMAT.md))
4. No empty Start Date column

### Q: 3D view is blank or black

**A:** Usually means WebGL isn't available:
1. Try toggling 3D off and on
2. Or use the canvas fallback (still works)
3. Try Chrome (best WebGL support)

See [FAQ about 3D](#3d-view) for more.

### Q: Video export is very slow

**A:** This is normal! Video encoding is computationally intensive.
- Keep the app in focus
- Don't close the window
- Let it finish (may take 5–30 minutes depending on settings)
- Try lower resolution/FPS if too slow

### Q: Where are my projects saved?

**A:**
- **macOS app**: Open the `.json` file in Finder (you chose the location when saving)
- **Web version**: No permanent save (reload loses data; use Download CSV or Publish)

### Q: Can I recover a deleted event?

**A:** Yes! Use **Edit › Undo** (⌘Z) immediately after deleting. If you've closed the app, reload your last saved project.

### Q: Why is file size so large?

**A:** If your project `.json` is large:
- Lots of events (100+)
- Large background images
- Encoded image data in the file

This is normal and not a problem.

## Getting Help

### I found a bug!

**Report it**: Open an issue on [GitHub Issues](https://github.com/dougalder/timeline-publisher/issues) with:
- What you did
- What happened
- Expected behavior
- macOS version and app version

### I have a feature request

**Suggest it**: [GitHub Discussions](https://github.com/dougalder/timeline-publisher/discussions) or open an issue with "enhancement" label

### I need help with my timeline

**Ask**: 
- GitHub Discussions
- Email: dougalder@icloud.com
- Check [MANUAL.md](MANUAL.md) for detailed guides

---

**Happy storytelling!** 📊✨

See [MANUAL.md](MANUAL.md) for complete feature documentation.
