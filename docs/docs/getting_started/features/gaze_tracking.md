# Gaze Tracking Process

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
│                  │
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



## 🎯 Step 2: Calibration

!!! important "Calibration = Accuracy"
    This is the most critical step! Good calibration means good data.

### What is Calibration?

Calibration teaches WebGazer where YOU look:

- **Machine Learning**: Builds a model unique to each user
- **Click-to-Gaze**: Correlates mouse clicks with eye position
- **Continuous**: Model improves throughout the session

### The Calibration Interface

Participants see a series of points that must be clicked to calibrate the model.

### Visual Feedback

Real-time feedback helps participants:

- ✅ **Change in color** - Point complete

## 👁️ Step 3: Gaze Tracking

### How It Works

Once calibrated, WebGazer continuously:

1. **Captures webcam frames** (60 fps)
2. **Detects face and eyes** (facial landmarks)
3. **Predicts gaze point** (machine learning model)
4. **Records coordinates** (x, y on screen)
5. **Stores data** (timestamped points)

### What Participants See

They only see the information of tasks. In prior studies conducted by the developers of WebGazer.js it was shown that gaze feedback was a distraction.

## 🖱️ Step 4: Mouse Tracking

### Simultaneous Collection

While tracking gaze, we also record mouse movements

## 📋 Step 5: Task Presentation

### Task Display

TODO: agregar una captura de como se muestran las tareas.


## 💾 Step 6: Data Storage

### Real-Time Saving

Data is saved continuously.

## 💡 Best Practices

### For Accurate Tracking

!!! success "Do's"
    - ✅ **Calibrate thoroughly** - Don't rush
    - ✅ **Good lighting** - Even, front-facing light
    - ✅ **Stable position** - Don't move around much
    - ✅ **Clear instructions** - Participants understand what to do
    - ✅ **Pilot test** - Test with a few people first

!!! failure "Don'ts"

    - ❌ **Skip calibration** - Data will be poor
    - ❌ **Backlit participants** - Windows behind them
    - ❌ **Moving heads** - Accuracy suffers
    - ❌ **Too many tasks** - Fatigue reduces quality
    - ❌ **Long sessions** - Keep under 20 minutes

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
- Works entirely in browser
- No server-side processing

**Cited in 1000+ research papers!**

### Browser Requirements

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 90+ | ✅ Full |
| Firefox | 88+ | ⚠️ Limited |
| Edge | 90+ | ⚠️ Limited |
| Safari | 14+ | ❌ Not supported |
| Mobile | Any | ❌ Not supported |

---

**Next Step:** [Managing Participants →](subjects.md)

**See also:** [Results & Analytics →](results.md)

**Back to:** [Features Overview →](../overview.md)