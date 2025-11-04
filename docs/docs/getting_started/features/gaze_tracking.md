# Eye Tracking Process

!!! success "The Magic Happens Here"
    This is where RemoteGazeUX transforms webcam data into insights. Let's explore how it works!

## 🎯 Overview

The eye tracking page is the heart of RemoteGazeUX. It handles:

1. **Webcam initialization** 📷
2. **Calibration** 🎯
3. **Real-time gaze tracking** 👁️
4. **Task presentation** 📋
5. **Data collection** 💾

All happening seamlessly in the browser!

## 🔄 The Complete Process

### Visual Flow

```
┌──────────────────┐
│  Webcam Access   │ ← User grants permission
│   Request        │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Camera Setup    │ ← WebGazer initializes
│  & Positioning   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Calibration     │ ← Click dots to train
│  (9-13 points)   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Validation      │ ← Check accuracy
│  (Optional)      │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Task 1          │ ← Present prototype
│  Execution       │   + Track gaze
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Task 2, 3...    │ ← Continue tasks
│  (Sequential)    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Data Saved      │ ← Store in database
│  Thank You!      │
└──────────────────┘
```

## 📷 Step 1: Webcam Access

### What Happens

When participants first arrive, they see a permission request:

> **"RemoteGazeUX wants to use your camera"**

### Technical Details

- **Browser API**: Uses `getUserMedia()` API
- **Privacy**: Camera data never leaves the browser
- **Requirements**: HTTPS for production (HTTP works locally)
- **Fallback**: Clear error if camera unavailable

### User Experience

!!! info "Participant View"
    ```
    ╔════════════════════════════════════╗
    ║  🎥 Camera Access Required         ║
    ║                                    ║
    ║  We need your camera to track      ║
    ║  where you look on the page.       ║
    ║                                    ║
    ║  Your video is NOT recorded or     ║
    ║  transmitted anywhere.             ║
    ║                                    ║
    ║     [Allow Camera Access]          ║
    ╚════════════════════════════════════╝
    ```

### Troubleshooting Access

**Common Issues:**

| Issue | Solution |
|-------|----------|
| Permission denied | Refresh and allow camera |
| No camera found | Check camera connection |
| Browser not supported | Use Chrome/Firefox/Edge |
| HTTPS required | Enable SSL or use localhost |

## 🎯 Step 2: Calibration

!!! important "Calibration = Accuracy"
    This is the most critical step! Good calibration means good data.

### What is Calibration?

Calibration teaches WebGazer where YOU look:

- **Machine Learning**: Builds a model unique to each user
- **Click-to-Gaze**: Correlates mouse clicks with eye position
- **Continuous**: Model improves throughout the session

### The Calibration Interface

Participants see a series of points:

```
     1           2           3
         
     
     4           5           6
     
     
     7           8           9
```

### Configuration Options

=== "9-Point (Recommended)"
    
    **Best balance of accuracy and time**
    
    ```json
    {
      "calibration_points": 9,
      "clicks_per_point": 5,
      "duration": "~2 minutes"
    }
    ```
    
    ✅ Good for most studies

=== "5-Point (Quick)"
    
    **Faster but less accurate**
    
    ```json
    {
      "calibration_points": 5,
      "clicks_per_point": 5,
      "duration": "~1 minute"
    }
    ```
    
    ⚠️ Use for quick tests only

=== "13-Point (High Accuracy)"
    
    **Maximum precision**
    
    ```json
    {
      "calibration_points": 13,
      "clicks_per_point": 5,
      "duration": "~3 minutes"
    }
    ```
    
    ✅ Research-grade accuracy

### Calibration Instructions

Participants see clear guidance:

!!! quote "On-Screen Instructions"
    **Step 1: Position Yourself**
    
    - Sit comfortably
    - Keep your head relatively still
    - Ensure good lighting
    - Look directly at each dot
    
    **Step 2: Click Each Dot**
    
    - Click each dot **5 times**
    - Look DIRECTLY at the dot while clicking
    - Take your time
    - Don't rush!

### Visual Feedback

Real-time feedback helps participants:

- ✅ **Green check** - Point complete
- 📊 **Progress bar** - "3/9 points done"
- 🎯 **Current target** - Highlighted dot
- ⏱️ **Timer** - Time per point

### Validation (Optional)

After calibration, test accuracy:

```
┌─────────────────────────────┐
│  Calibration Complete!      │
│                             │
│  Accuracy: 87%  ✅          │
│                             │
│  Look at the red dot...     │
│        •                    │
│  (Don't click, just look)   │
│                             │
│  [Continue] [Re-calibrate]  │
└─────────────────────────────┘
```

If accuracy < 75%, prompt re-calibration.

## 👁️ Step 3: Gaze Tracking

### How It Works

Once calibrated, WebGazer continuously:

1. **Captures webcam frames** (60 fps)
2. **Detects face and eyes** (facial landmarks)
3. **Predicts gaze point** (machine learning model)
4. **Records coordinates** (x, y on screen)
5. **Stores data** (timestamped points)

### What Participants See

**Visual feedback (optional):**

- 🔴 **Red dot** - Shows current gaze point
- 🎯 **Fade trail** - Recent gaze history
- 📊 **Task info** - Current task description

!!! tip "Toggle Gaze Indicator"
    You can hide the red dot to prevent influencing behavior:
    
    ```json
    {
      "show_gaze_indicator": false
    }
    ```

### Data Being Collected

Every ~16ms (60 Hz), we record:

```javascript
{
  timestamp: 1698765432.123,      // Millisecond precision
  x: 450,                         // Screen X coordinate
  y: 320,                         // Screen Y coordinate
  task_id: 1,                     // Current task
  element_id: "button_login",     // Hovered element (if any)
  fixation: true,                 // Is this a fixation?
  saccade: false                  // Is this a saccade?
}
```

### Fixation Detection

**Automatic fixation classification:**

- **Fixation**: Eyes relatively still (reading, examining)
  - Duration: > 100ms
  - Movement: < 50 pixels
  
- **Saccade**: Rapid eye movement (scanning)
  - Duration: 20-100ms
  - Movement: > 50 pixels

## 🖱️ Step 4: Mouse Tracking

### Simultaneous Collection

While tracking gaze, we also record:

**Mouse Movements:**
```javascript
{
  timestamp: 1698765432.456,
  type: "mousemove",
  x: 452,
  y: 318,
  velocity: 234  // pixels/second
}
```

**Mouse Clicks:**
```javascript
{
  timestamp: 1698765433.789,
  type: "click",
  x: 450,
  y: 320,
  button: "left",
  element_id: "button_login",
  element_text: "Log In"
}
```

**Scroll Events:**
```javascript
{
  timestamp: 1698765434.012,
  type: "scroll",
  scroll_x: 0,
  scroll_y: 450,
  direction: "down"
}
```

## 📋 Step 5: Task Presentation

### Task Display

Each task shows:

```
┌───────────────────────────────────────┐
│ Task 1 of 3                    0:45   │
│                                        │
│ Find the login button and click it    │
└───────────────────────────────────────┘
```

- **Task number** - Progress tracking
- **Timer** - Countdown or count-up
- **Instructions** - What to do
- **Prototype** - Below the task bar

### Task Timing

=== "Fixed Duration"
    
    **Auto-advance after time limit**
    
    ```json
    {
      "task_id": 1,
      "description": "Find the pricing page",
      "duration": 30,
      "auto_advance": true
    }
    ```

=== "User-Paced"
    
    **Participant clicks "Next"**
    
    ```json
    {
      "task_id": 1,
      "description": "Explore the homepage",
      "duration": null,
      "show_next_button": true
    }
    ```

=== "Success-Triggered"
    
    **Auto-advance on completion**
    
    ```json
    {
      "task_id": 1,
      "description": "Click the login button",
      "target_element": "#login-button",
      "auto_advance_on_click": true
    }
    ```

### Between Tasks

Brief pause with feedback:

```
┌───────────────────────────┐
│  Task 1 Complete! ✅      │
│                           │
│  Next: Find the search    │
│        feature            │
│                           │
│  [Continue]               │
└───────────────────────────┘
```

## 💾 Step 6: Data Storage

### Real-Time Saving

Data is saved continuously:

- **Every second** - Batch insert to database
- **Async processing** - No lag for participant
- **Error recovery** - Retry on failure
- **Session ID** - All data linked to participant

### Database Schema

```sql
-- Gaze data table
CREATE TABLE gaze_points (
    id INTEGER PRIMARY KEY,
    session_id TEXT,
    task_id INTEGER,
    timestamp REAL,
    x INTEGER,
    y INTEGER,
    is_fixation BOOLEAN,
    element_id TEXT
);

-- Mouse data table  
CREATE TABLE mouse_events (
    id INTEGER PRIMARY KEY,
    session_id TEXT,
    task_id INTEGER,
    timestamp REAL,
    event_type TEXT,
    x INTEGER,
    y INTEGER,
    element_id TEXT
);
```

### Data Integrity

Ensuring quality:

- ✅ **Validation** - Check reasonable coordinates
- ✅ **Timestamps** - Monotonic increase
- ✅ **Task linkage** - Proper task association
- ✅ **Completeness** - No gaps in timeline

## 🎨 Customization Options

### Visual Appearance

```json
{
  "tracking_page": {
    "show_task_timer": true,
    "show_progress_bar": true,
    "show_gaze_indicator": true,
    "gaze_indicator_color": "#FF0000",
    "gaze_indicator_size": 10,
    "task_bar_position": "top",
    "background_color": "#FFFFFF"
  }
}
```

### Tracking Behavior

```json
{
  "tracking": {
    "sample_rate": 60,              // Hz
    "smooth_factor": 0.5,           // 0-1, higher = smoother but less responsive
    "store_raw_data": true,         // Keep unprocessed data
    "fixation_threshold_ms": 100,   // Min fixation duration
    "saccade_threshold_px": 50      // Min movement for saccade
  }
}
```

### Calibration Settings

```json
{
  "calibration": {
    "point_count": 9,
    "clicks_per_point": 5,
    "point_duration": null,         // null = no time limit
    "show_validation": true,
    "min_accuracy": 0.75,           // Require 75% accuracy
    "allow_recalibration": true
  }
}
```

## 💡 Best Practices

### For Accurate Tracking

!!! success "Do's"
    ✅ **Calibrate thoroughly** - Don't rush
    ✅ **Good lighting** - Even, front-facing light
    ✅ **Stable position** - Don't move around much
    ✅ **Clear instructions** - Participants understand what to do
    ✅ **Pilot test** - Test with a few people first

!!! failure "Don'ts"
    ❌ **Skip calibration** - Data will be poor
    ❌ **Backlit participants** - Windows behind them
    ❌ **Moving heads** - Accuracy suffers
    ❌ **Too many tasks** - Fatigue reduces quality
    ❌ **Long sessions** - Keep under 20 minutes

### For Better Data Quality

1. **Instruct participants:**
   - Sit still
   - Look naturally
   - Don't overthink
   - Be honest in responses

2. **Environment setup:**
   - Good lighting
   - Quiet space
   - No distractions
   - Comfortable chair

3. **Task design:**
   - Clear objectives
   - Reasonable time limits
   - Not too complex
   - Natural scenarios

## 🔧 Technical Details

### WebGazer.js

**What is it?**
- Open-source eye tracking library
- Uses TensorFlow.js for ML
- Works entirely in browser
- No server-side processing

**How accurate?**
- Typical: 50-100 pixels
- With good calibration: 30-50 pixels
- Depends on: lighting, webcam quality, calibration

**Cited in 1000+ research papers!**

### Browser Requirements

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 90+ | ✅ Full |
| Firefox | 88+ | ✅ Full |
| Edge | 90+ | ✅ Full |
| Safari | 14+ | ⚠️ Limited |
| Mobile | Any | ❌ Not supported |

### Performance

**Resource usage:**
- CPU: 5-15% (varies by hardware)
- RAM: ~100-200 MB
- Network: Minimal (only sends data points)
- Storage: ~1 MB per 10-minute session

## 📊 Data Output

### What You Get

For each participant session:

**Gaze data CSV:**
```csv
session_id,task_id,timestamp,x,y,fixation,element_id
S001,1,1698765432.123,450,320,true,button_login
S001,1,1698765432.139,452,321,true,button_login
...
```

**Mouse data CSV:**
```csv
session_id,task_id,timestamp,type,x,y,element_id
S001,1,1698765433.456,click,450,320,button_login
S001,1,1698765434.789,move,500,350,null
...
```

**Metadata JSON:**
```json
{
  "session_id": "S001",
  "start_time": "2024-11-04T14:30:00Z",
  "end_time": "2024-11-04T14:40:15Z",
  "total_duration": 615,
  "tasks_completed": 3,
  "calibration_accuracy": 0.87,
  "total_gaze_points": 36900,
  "total_mouse_events": 45
}
```

## 🆘 Troubleshooting

### Calibration Issues

**Poor accuracy (<70%)?**
- Re-calibrate
- Improve lighting
- Check camera position
- Ensure participant understands process

**Calibration won't complete?**
- Check JavaScript console
- Verify webcam access
- Try different browser
- Restart session

### Tracking Issues

**Gaze point jumping around?**
- Participant moving too much
- Poor lighting
- Need re-calibration
- Adjust smoothing factor

**No gaze data recorded?**
- Check browser console
- Verify database connection
- Check permissions
- Ensure WebGazer loaded

**Prototype not loading?**
- Check URL is accessible
- Verify CORS settings
- Check prototype type setting
- Try different URL

---

**Next Step:** [Managing Participants →](subjects.md)

**See also:** [Results & Analytics →](results.md)

**Back to:** [Features Overview →](../overview.md)