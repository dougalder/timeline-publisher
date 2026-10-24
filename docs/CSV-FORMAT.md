# CSV Format Guide

How to prepare spreadsheet data for import into Timeline Publisher.

## Basic Format

Timeline Publisher imports CSV (Comma-Separated Values) files. Create one in any spreadsheet app:
- Excel, Google Sheets, Numbers
- Export as `.csv` file
- Import into Timeline Publisher via File › Import CSV

## Required Columns

Your CSV **must** have at least these columns (header row required):

| Column | Required | Format | Example |
|--------|----------|--------|---------|
| **Title** | Yes | Text | "Graduated High School" |
| **Start Date** | Yes | See below | "2020-06-15" |
| **End Date** | No | See below | "2020-08-31" |
| **Description** | No | Text | "Top of class, scholarship awarded" |

## Optional Columns

Add these columns for better organization:

| Column | Effect | Example |
|--------|--------|---------|
| **Track** | Assigns to color-coded category | "Education", "Career", "Family" |
| **Color** | Custom event color | "#FF6B6B" (hex) |
| **URL** | Makes title clickable | "https://example.com" |
| **Image** | Background image for event | "photo.jpg" |

## Date Formats

Any of these date formats work:

| Format | Example | Use Case |
|--------|---------|----------|
| `YYYY-MM-DD` | 2020-06-15 | **Recommended**: Most precise, unambiguous |
| `YYYY-MM` | 2020-06 | Month + year only |
| `YYYY` | 2020 | Year only (event spans whole year) |
| `MM/DD/YYYY` | 06/15/2020 | US date format (converted to ISO) |
| `DD/MM/YYYY` | 15/06/2020 | International format |
| ISO 8601 | 2020-06-15T14:30:00Z | With time (time is ignored) |

**Tips**:
- Use `YYYY-MM-DD` to avoid ambiguity
- For "2020" only, the event covers the whole year
- Time component is ignored (events are day-based)
- Invalid dates are skipped with warning

## CSV Examples

### Example 1: Personal Timeline

```csv
Title,Start Date,End Date,Description,Track
Born,1980-06-15,,Started my life,Life Events
Graduated High School,1998-06-15,,Top of class,Education
Started College,1998-09-01,2002-05-31,University of example,Education
Got First Job,2002-07-15,,Software engineer at TechCorp,Career
Got Married,2005-08-20,,Married Jane Doe,Life Events
First Child Born,2007-03-10,,Had son Alex,Family
Started Own Company,2010-01-15,,Founded StartupCorp,Career
Second Child Born,2012-09-22,,Had daughter Sophie,Family
Major Book Released,2015-03-01,,Wrote "My Story",Life Events
```

### Example 2: Company History

```csv
Title,Start Date,End Date,Description,Track,Color
Founded,2010-01-15,,Started with 3 people,Company,#3498db
First Hire,2010-06-01,,Hired first employee,Company,#3498db
Series A Funding,2011-06-15,,Raised $2M,Funding,#e74c3c
Product Launch,2012-03-01,,Released to public,Product,#2ecc71
100 Employees,2013-12-31,,Hit major milestone,Team,#9b59b6
Acquired by Google,2015-05-15,,Successful exit,Company,#f39c12
```

### Example 3: Historical Timeline

```csv
Title,Start Date,End Date,Description,Track
Declaration of Independence,1776-07-04,,American independence declared,Political
Industrial Revolution Begins,1760,,Start of mechanization era,Technology
First Telegraph Transmitted,1844-05-24,,"What hath God wrought" message,Technology
Gold Rush Begins,1848-01-24,,Gold discovered in California,Economics
Civil War,1861-04-12,1865-04-15,,American conflict,Political
Transcontinental Railroad Complete,1869-05-10,,East meets West,Technology
```

## Column Headers

Headers must be in the first row. These exact names are recognized:

**Automatically Detected**:
- Title, Start Date, End Date, Description (exact match)
- Date, Start, End, Duration
- Summary, Notes, Comments, Details
- Category, Track, Type, Group

**Best Practice**:
Use standard names: `Title`, `Start Date`, `End Date`, `Description`, `Track`

If your headers don't match exactly, Timeline Publisher asks you to map columns during import.

## Importing in Timeline Publisher

1. **Export CSV from spreadsheet**:
   - Excel: File › Save As › `.csv` format
   - Google Sheets: File › Download › `.csv`
   - Numbers: File › Export › CSV

2. **Import into Timeline Publisher**:
   - File › Import CSV
   - Choose your CSV file
   - Select which Track the data belongs to (or create new)
   - Choose mode: Add to existing / Replace all

3. **Review & Edit**:
   - Data tab shows imported events
   - Edit any event by clicking it
   - Timeline updates in real-time

## Tips for Clean Data

### Good Data

```csv
Title,Start Date,End Date,Description,Track
Moved to NYC,2020-01-15,,New chapter begins,Life
Promotion at work,2020-06-01,,Became team lead,Career
```

✅ Consistent format (all dates same format)
✅ Clear titles (searchable, descriptive)
✅ Proper tracks (same spelling every time)

### Problem Data (Will Fix)

```csv
Title,Start Date,End Date,Description,Track
Moved to New York,20200115,,New chapter,Moving
Promotion,6/1/2020,,Became team lead,CAREER
Got married,May 2021,,Jane Doe,Life
```

⚠️ Date format inconsistency (but will be converted)
⚠️ Track case differences (normalized to lowercase)
⚠️ Mixed date formats (still works)

All of these examples will import successfully—Timeline Publisher normalizes formats.

## Empty Fields

Fields can be left empty (no problem):

```csv
Title,Start Date,End Date,Description,Track
Event with no date,,,Placeholder,Unknown
Event without end,2020-01-01,,Ongoing,Projects
Event without description,2020-06-15,,
```

- **Start Date** is required (at least)
- **End Date** is optional (event becomes single point in time)
- **Description** optional (shows blank)
- **Track** optional (goes to "Uncategorized")

## Special Characters

CSV handles special characters:

```csv
Title,Start Date,Description
"Café opening in Paris",2020-04-15,"Bonjour! C'est magnifique!"
"Smith & Sons, Ltd.",2019-01-01,"Ampersand & symbols work fine"
"Quotes inside ""nested"" properly",2018-06-01,"Use double quotes to escape"
```

✅ Unicode works fine (é, ñ, 中文, etc.)
✅ Quotes must be escaped with double-quotes
✅ Commas inside fields work if field is quoted

## Size & Performance

- **Small files** (< 100 events): Instant import
- **Medium files** (100-1000 events): < 5 seconds
- **Large files** (1000+ events): 5-10 seconds

Performance is fine for most datasets. Very large imports may slow down rendering slightly (still functional).

## Troubleshooting

### Dates not importing correctly

**Problem**: Events don't appear or appear on wrong dates

**Solutions**:
- Use `YYYY-MM-DD` format consistently
- Check for typos in date fields
- Ensure Start Date column isn't empty
- Verify no leading/trailing spaces in dates

**Example CSV fix**:
```csv
Title,Start Date
Event A,2020-01-15    # Good
Event B, 2020-02-15   # Bad (space before date)
Event C,2020-02-31    # Bad (invalid date)
```

### Tracks not grouping together

**Problem**: Same track appears as multiple tracks

**Solutions**:
- Check for case differences: "Career" vs "career" vs "CAREER"
- Remove extra spaces: "Career " vs "Career"
- Use consistent spelling: "Tech" vs "Technology"

Timeline Publisher normalizes to lowercase, so these will merge:
- "Career", "CAREER", "career" → all become same track ✓

But these stay separate:
- "Tech" vs "Technology" → two different tracks

### Special characters causing issues

**Problem**: Chinese characters, accents, symbols not importing

**Solutions**:
- Make sure CSV is saved as UTF-8 (not ASCII)
- In Excel: File › Save As › CSV UTF-8
- In Google Sheets: Download › CSV (UTF-8 by default) ✓

## Exporting Back to CSV

After editing in Timeline Publisher:

1. Make changes in the app
2. Choose **File › Download CSV**
3. CSV file contains all current events
4. Reimport to another project or share with team

Exported CSV includes:
- All tracks and events
- Current styling and colors
- Timestamps of import

## Integration with Other Tools

### Syncing with Google Sheets

To keep Timeline Publisher synced with Google Sheets:

1. **Edit in Google Sheets**
2. **Periodically export**: Google Sheets › File › Download › CSV
3. **Reimport**: File › Import CSV › Replace all data

### Exporting for Excel

Timeline Publisher exports work in Excel:

1. **Download CSV** from Timeline Publisher
2. **Open in Excel**: File › Open
3. **Save as** `.xlsx` if needed

All data imports/exports preserve:
- Date information
- Track assignments
- Descriptions
- Colors and styling

## CSV Template

Use this template to start:

```csv
Title,Start Date,End Date,Description,Track
Example Event 1,2020-01-15,,First event description,Category A
Example Event 2,2020-06-01,2020-08-31,Multi-day event,Category B
Example Event 3,2021-01-01,,Another event,Category A
```

---

Need more help? See:
- [MANUAL.md](MANUAL.md) — Complete user guide
- [INSTALL.md](INSTALL.md) — Installation & setup
- [FAQ.md](FAQ.md) — Answers to common questions

Happy data importing! 📊
