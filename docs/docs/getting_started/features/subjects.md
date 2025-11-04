# Managing Participants

!!! info "Your Command Center"
    The Subjects page is where you manage all your participant data and access results. Think of it as your research dashboard!

## 🎯 Overview

The **Subjects Management Page** (`/sujetos`) is your central hub for:

- 📊 Viewing all participants
- 🔍 Filtering and searching
- 📈 Accessing individual results
- 📥 Downloading data
- 🗑️ Managing participant records

**Access:** Requires admin login (protected route)

## 🌟 Key Features

### Multi-Study Organization

Run multiple studies? Each gets its own tab!

```
┌─────────────────────────────────────────┐
│ 📊 Participant Dashboard                │
├─────────────────────────────────────────┤
│  Study 1  │  Study 2  │  Study 3  │ +   │
├─────────────────────────────────────────┤
│                                         │
│  📋 Navigation Usability Study          │
│  ───────────────────────────────────    │
│                                         │
│  Total Participants: 45                 │
│  Completed: 42 | In Progress: 3         │
│  Average Duration: 8m 34s               │
│                                         │
│  [Download All Data]                    │
└─────────────────────────────────────────┘
```

### Participant List

Clean, sortable table of all participants:

| ID | Name | Age | Gender | Date | Duration | Status | Actions |
|----|------|-----|--------|------|----------|--------|---------|
| P001 | John Doe | 25 | M | Nov 4, 2024 | 9m 15s | ✅ Complete | 👁️ 📊 🗑️ |
| P002 | Jane Smith | 32 | F | Nov 4, 2024 | 7m 42s | ✅ Complete | 👁️ 📊 🗑️ |
| P003 | Alex Johnson | 28 | NB | Nov 4, 2024 | 3m 20s | ⏸️ In Progress | 👁️ 📊 🗑️ |

**Features:**
- ✅ Sortable columns (click headers)
- 🔍 Search by name, ID, or any field
- 📅 Filter by date range
- 🎯 Filter by completion status
- 📊 Quick stats at a glance

### Quick Actions

For each participant:

| Icon | Action | Description |
|------|--------|-------------|
| 👁️ | **View Details** | See participant info and session summary |
| 📊 | **View Results** | Open heatmaps and visualizations |
| 📥 | **Download Data** | Get CSV export for this participant |
| 🗑️ | **Delete** | Remove participant (with confirmation) |

## 📊 Study Overview

### Study Summary Cards

Each study shows:

```
╔═════════════════════════════════════════╗
║  Navigation Usability Study             ║
║  Created: Oct 15, 2024                  ║
╟─────────────────────────────────────────╢
║  📊 Statistics                          ║
║  ────────────────────                   ║
║  Total Participants:        45          ║
║  Completed Sessions:        42          ║
║  In Progress:               3           ║
║  Average Duration:          8m 34s      ║
║  Average Age:               29.5 years  ║
║  Male/Female/Other:         20/18/7     ║
║                                         ║
║  📅 Date Range                          ║
║  First Participant:  Oct 20, 2024       ║
║  Most Recent:        Nov 4, 2024        ║
║                                         ║
║  [📥 Download All]  [📊 Analytics]      ║
╚═════════════════════════════════════════╝
```

### Study-Level Actions

**Download All Data** 📥
- Combined CSV with all participants
- Separate files for gaze and mouse data
- Metadata JSON file
- Summary statistics

**View Analytics** 📊
- Aggregate heatmaps
- Comparison charts
- Task completion rates
- Time-on-task analysis

## 🔍 Filtering & Search

### Search Bar

**Universal search across all fields:**

```
┌─────────────────────────────────────┐
│  🔍 Search participants...          │
└─────────────────────────────────────┘
```

Search by:
- Participant name
- Participant ID
- Age
- Gender
- Any demographic field
- Completion status
- Date

**Example searches:**
- "John" - Find all Johns
- "25" - Find 25-year-olds
- "Male" - Filter by gender
- "Complete" - Only completed sessions
- "Nov 4" - Specific date

### Advanced Filters

```
┌─────────────────────────────────────┐
│  🎚️ Advanced Filters                │
├─────────────────────────────────────┤
│  Status:      [All ▼]               │
│  Date Range:  [Last 30 days ▼]     │
│  Age Range:   18 ─────────── 65    │
│  Gender:      [All ▼]               │
│  Duration:    [Any ▼]               │
│                                     │
│  [Apply Filters]  [Reset]           │
└─────────────────────────────────────┘
```

### Sorting

Click any column header to sort:

- **Name** - Alphabetical (A-Z or Z-A)
- **Age** - Numeric (ascending or descending)
- **Date** - Chronological (newest or oldest first)
- **Duration** - Session length (longest or shortest first)
- **Status** - Completion status

## 👤 Participant Details

Click **View Details** (👁️) to see full information:

### Session Overview

```
╔═════════════════════════════════════════╗
║  Participant Details                    ║
║  ID: P001                               ║
╟─────────────────────────────────────────╢
║  📋 Demographics                        ║
║  Name:           John Doe               ║
║  Age:            25                     ║
║  Gender:         Male                   ║
║  Experience:     Intermediate           ║
║  Device:         Chrome on macOS        ║
║                                         ║
║  ⏱️ Session Information                 ║
║  Started:        Nov 4, 2024 2:30 PM    ║
║  Completed:      Nov 4, 2024 2:39 PM    ║
║  Duration:       9 minutes 15 seconds   ║
║  Status:         ✅ Complete            ║
║                                         ║
║  🎯 Task Completion                     ║
║  Task 1: Find login        ✅ 0:45      ║
║  Task 2: Locate pricing    ✅ 1:23      ║
║  Task 3: Find support      ✅ 0:58      ║
║                                         ║
║  📊 Data Quality                        ║
║  Calibration Accuracy:  87%             ║
║  Gaze Points Collected: 33,450          ║
║  Mouse Events:          127             ║
║  Data Completeness:     ✅ 100%         ║
║                                         ║
║  [📊 View Results]  [📥 Download CSV]   ║
╚═════════════════════════════════════════╝
```

### Task Timeline

Visual timeline of task progression:

```
Task 1: Find Login Button
├─ 0:00 - 0:05  Calibration
├─ 0:05 - 0:12  Reading instructions
├─ 0:12 - 0:45  Searching for button
└─ 0:45         ✅ Button clicked

Task 2: Locate Pricing
├─ 0:45 - 0:50  Reading task
├─ 0:50 - 1:20  Scanning page
├─ 1:20 - 1:55  Reading pricing table
└─ 1:55         ✅ Task completed

Task 3: Find Support
├─ 1:55 - 2:00  Reading task
├─ 2:00 - 2:40  Looking for support links
└─ 2:40         ✅ Support found
```

## 📥 Data Export

### Individual Export

For a single participant:

**CSV Format:**
```csv
participant_id,task_id,timestamp,x,y,event_type,element_id
P001,1,1698765432.123,450,320,gaze,null
P001,1,1698765432.139,452,321,gaze,null
P001,1,1698765433.456,450,320,click,button_login
...
```

**JSON Format:**
```json
{
  "participant": {
    "id": "P001",
    "name": "John Doe",
    "demographics": {...}
  },
  "session": {
    "start_time": "2024-11-04T14:30:00Z",
    "end_time": "2024-11-04T14:39:15Z",
    "duration": 555
  },
  "tasks": [...],
  "gaze_data": [...],
  "mouse_data": [...]
}
```

### Bulk Export

Download all participants at once:

**What you get:**
```
study_navigation_export/
├── combined_data.csv
├── metadata.json
├── participants/
│   ├── P001_gaze.csv
│   ├── P001_mouse.csv
│   ├── P002_gaze.csv
│   ├── P002_mouse.csv
│   └── ...
├── summary_statistics.csv
└── README.txt
```

**File descriptions:**

| File | Contents |
|------|----------|
| `combined_data.csv` | All participants, all data points |
| `metadata.json` | Study config, participant demographics |
| `participants/*.csv` | Individual participant files |
| `summary_statistics.csv` | Aggregate metrics per participant |
| `README.txt` | Data dictionary and usage notes |

## 🎨 Customization

### Column Configuration

Choose which columns to display:

```json
{
  "subjects_page": {
    "visible_columns": [
      "id",
      "name",
      "age",
      "gender",
      "date",
      "duration",
      "status"
    ],
    "default_sort": {
      "column": "date",
      "order": "desc"
    }
  }
}
```

### Custom Demographics Display

Show your custom form fields:

```json
{
  "subjects_page": {
    "visible_columns": [
      "id",
      "name",
      "experience_level",  // Custom field
      "design_preference", // Custom field
      "date",
      "status"
    ]
  }
}
```

## 🔐 Access Control

### User Roles

Different access levels:

| Role | View Participants | Download Data | Delete | Edit Config |
|------|-------------------|---------------|--------|-------------|
| **Admin** | ✅ | ✅ | ✅ | ✅ |
| **Researcher** | ✅ | ✅ | ❌ | ❌ |
| **Viewer** | ✅ | ❌ | ❌ | ❌ |

### Session Management

**Auto-logout:** After 1 hour of inactivity

**Multi-device:** Can login from multiple devices

**Activity log:** Track who accessed what data

## 📊 Analytics Dashboard

### Aggregate Statistics

See patterns across all participants:

**Demographics Breakdown:**
```
Age Distribution
18-24: ████████░░ 35%
25-34: ██████████ 45%
35-44: ████░░░░░░ 15%
45+:   ██░░░░░░░░  5%

Gender Distribution
Male:   ████████░░ 44%
Female: █████████░ 40%
Other:  ████░░░░░░ 16%
```

**Performance Metrics:**
```
Average Session Duration:  8m 34s
Median Session Duration:   8m 12s
Shortest Session:          4m 23s
Longest Session:          15m 47s

Task Completion Rates:
Task 1: ████████████████ 98% (44/45)
Task 2: ██████████████░░ 93% (42/45)
Task 3: ███████████████░ 96% (43/45)
```

### Comparison Tools

**Compare participants side-by-side:**

| Metric | P001 | P002 | P003 | Average |
|--------|------|------|------|---------|
| Duration | 9m 15s | 7m 42s | 8m 01s | 8m 34s |
| Task 1 Time | 0:45 | 0:38 | 0:52 | 0:46 |
| Task 2 Time | 1:23 | 1:15 | 1:28 | 1:20 |
| Gaze Points | 33,450 | 27,820 | 28,940 | 30,500 |
| Cal. Accuracy | 87% | 92% | 81% | 85% |

## 🗑️ Data Management

### Delete Participant

With confirmation dialog:

```
╔═══════════════════════════════════╗
║  ⚠️ Delete Participant?           ║
║                                   ║
║  Are you sure you want to delete  ║
║  participant P001 (John Doe)?     ║
║                                   ║
║  This will permanently delete:    ║
║  • All gaze data                  ║
║  • All mouse data                 ║
║  • Session recordings             ║
║  • Demographic information        ║
║                                   ║
║  ⚠️ This cannot be undone!        ║
║                                   ║
║  [Cancel]  [Yes, Delete]          ║
╚═══════════════════════════════════╝
```

### Anonymize Data

Remove personally identifiable information:

```
╔═══════════════════════════════════╗
║  🔒 Anonymize Participant?        ║
║                                   ║
║  This will remove:                ║
║  ✅ Name                          ║
║  ✅ Email                         ║
║  ✅ IP address                    ║
║                                   ║
║  This will keep:                  ║
║  ✅ Age (range only)              ║
║  ✅ Gender                        ║
║  ✅ All gaze/mouse data           ║
║  ✅ Aggregate statistics          ║
║                                   ║
║  [Cancel]  [Anonymize]            ║
╚═══════════════════════════════════╝
```

### Bulk Operations

Select multiple participants:

```
☑️ Select All  |  [📥 Download Selected]  [🗑️ Delete Selected]

☑️ P001 - John Doe       Nov 4, 2024    9m 15s
☑️ P002 - Jane Smith     Nov 4, 2024    7m 42s
☐ P003 - Alex Johnson   Nov 4, 2024    8m 01s
☑️ P004 - Sam Lee        Nov 3, 2024   10m 23s
```

## 💡 Pro Tips

### Efficient Workflows

!!! success "Best Practices"
    
    **During Data Collection:**
    - Check participant list regularly
    - Monitor completion rates
    - Identify and address dropouts quickly
    
    **After Collection:**
    - Download raw data immediately
    - Back up to multiple locations
    - Anonymize before sharing
    
    **For Analysis:**
    - Use filters to segment participants
    - Compare high vs low performers
    - Export to your analysis tool of choice

### Data Quality Checks

**Red flags to watch for:**

| Issue | What It Means | Action |
|-------|---------------|--------|
| Duration < 2 min | Likely quit early | Review and possibly exclude |
| Cal. accuracy < 70% | Poor tracking quality | Consider re-running |
| 0 mouse clicks | No interaction | Investigate |
| Incomplete tasks | Didn't finish | Contact participant |

## 🔧 Configuration

### Page Settings

```json
{
  "subjects_page": {
    "items_per_page": 25,
    "show_demographics": true,
    "show_session_stats": true,
    "allow_download": true,
    "allow_delete": true,
    "require_delete_confirmation": true,
    "enable_search": true,
    "enable_filters": true,
    "enable_bulk_actions": true
  }
}
```

### Privacy Settings

```json
{
  "privacy": {
    "show_participant_names": true,
    "show_ip_addresses": false,
    "auto_anonymize_after_days": 365,
    "allow_participant_data_requests": true
  }
}
```

## 🆘 Troubleshooting

**Page not loading?**
- Check if logged in
- Verify database connection
- Check browser console for errors

**Can't see participants?**
- Check study filter
- Verify participants completed registration
- Check database has data

**Export not working?**
- Check file permissions
- Verify CSV generation
- Try smaller date range

**Missing data?**
- Check participant completed session
- Verify tracking was enabled
- Check data collection logs

---

**Next:** [Analyzing Results →](results.md)

**See also:** [Data Export Guide](../../api_reference/rest_api.md)

**Back to:** [Features Overview →](../overview.md)