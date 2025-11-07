# Quick Start Guide

!!! success "Your First Eye-Tracking Study in 5 Minutes"
    Follow this guide to run your first study from start to finish. By the end, you'll have collected real eye-tracking data!

## 🎯 What You'll Accomplish

In this quick start, you'll:

1. ✅ Set up a simple eye-tracking study
2. ✅ Test it yourself as a participant
3. ✅ View beautiful heatmap visualizations
4. ✅ Export your data

Let's go! 🚀

## Step 1: Launch RemoteGazeUX

Open your terminal and start the application:

```bash
cd RemoteGazeUX
python run.py
```

After being asked to modify your configuration, create admin users you should see:

```
✨ RemoteGazeUX is running!
🔗 URL: https://localhost:5001
```

!!! tip "Keep this terminal window open"
    The application runs here. You'll see helpful logs as participants connect.

## Step 2: Create Your Study

### Use the Configuration GUI

When running RemoteGazeUX you should see

```
Do you want to modify configurations before running the application? (y/n):
```

Inputting yes will open a GUI for setting a new prototype URL, a different port or also change the tasks.

Also, you can open this GUI with:

```bash
python src/config.py
```

A friendly GUI window appears! 🎨

TODO: hacer captura

![Configuration GUI](../assets/config_gui.png)

**Fill in your study details:**

- **Study Name**: "My First Eye-Tracking Test"
- **Prototype URL**: Use the demo or your own Figma prototype
  - Demo: `https://www.figma.com/proto/example` (try a real Figma link!)
  - Or upload an image path: `/path/to/your/image.png`
- **Tasks**: Define what participants should do
  - Task 1: "Find the login button"
  - Task 2: "Locate the search feature"

Click **Save** ✅


## Step 3: Test as a Participant

Now for the fun part — experience what your participants will see!

### 3.1 Open the Study

Navigate to: `http://localhost:5000`

### 3.2 Fill the Entry Form

You'll see a clean registration form:

![Entry Form](../assets/docs/quickstart/entry-form.png)


Fill in test data:

- **Name**: Test
- **Surname**: User
- **Age**: 25

Click **Submit** 🎯

### 3.3 Calibration

!!! important "Calibration is Key"
    Good calibration = accurate eye-tracking data. Take your time here!

You'll see a series of dots on screen:

1. **Sit comfortably** - Keep your head relatively still
2. **Click each dot** - Look directly at each point when clicking
3. **Click 5 times** per dot when prompted
4. **Follow instructions** carefully

![Calibration](../assets/calibration.png)

!!! tip "Pro Tip"
    Room lighting matters! Avoid backlighting (windows behind you) for best results.

### 3.4 Complete the Tasks

After calibration, you'll see your prototype with task instructions:

- **Task instructions** appear at the top

**Just interact naturally!** Look around, click things, explore the interface.

![Tracking Session](../assets/tracking.png)

### 3.5 Finish

When all tasks are complete, you'll see a thank you message. 

**Congratulations!** You've just collected your first eye-tracking data! 🎉

## Step 4: View Your Results

Now for the exciting part — see what you tracked!

### 4.1 Access the Admin Panel

Navigate to: `http://localhost:5000/sujetos`

Login with your admin credentials.

### 4.2 Explore Your Data

![Admin Panel](../assets/admin_panel.png)

You'll see:

- **Studies tab** - All your studies
- **Participants list** - Click on "Test User"
- **Session details** - Timestamp, duration, task completion

### 4.3 View the Heatmap

Click **"View Results"** for your test participant.

![Heatmap](../assets/heatmap.png)

**Wow!** 🤯 This heatmap shows:

- 🔥 **Hot spots** (red/yellow) - Where you looked most
- 🧊 **Cold spots** (blue/green) - Areas you ignored
- ⚫ **Blind spots** - Never looked at

### 4.4 Analyze the Data

Toggle through different visualizations:

- **Static Heatmap** - Overall attention distribution
- **Gaze Plot** - Sequential path of eye movements
- **Mouse Track** - Where you clicked and moved

!!! tip "Publication-Ready Graphics"
    These visualizations are high-quality and ready for presentations or papers!

## Step 5: Export Your Data

Want to analyze the raw data? Easy!

### Export Individual Session

On the results page, click **"Download CSV"**

You'll get a file with columns:
```csv
date,x_mouse,y_mouse,x_gaze,y_gaze
2025-10-16 11:32:36,0.0,0.0,1399.614608374622,485.90008997831643
2025-10-16 11:32:36,0.0,0.0,1173.1436953906164,400.8048705042029
2025-10-16 11:32:36,0.0,0.0,1097.997644500679,373.6929253870312
2025-10-16 11:32:36,0.0,0.0,1908.0,0.0
...
```

Perfect for analysis in Python, R, Excel, or your favorite tool!

### Export Entire Study

From the studies page, click **"Download All Data"** to get all participants data.

## 🎓 You Did It!

In just 10 minutes, you've:

- ✅ Set up a study
- ✅ Collected eye-tracking data
- ✅ Generated professional visualizations
- ✅ Exported data for analysis

## 🚀 Next Steps

Now that you know the basics, level up:


=== "Customize Your Study"
    
    **Make it Your Own:**
    
    - Add more tasks
    - Use your own prototypes
    
    [Configuration guide →](configuration.md)

=== "Analyze Results"
    
    **Deep Dive into Data:**
    
    - Statistical analysis
    - Comparison between participants
    - Task performance metrics
    - Attention mapping
    

=== "Advanced Features"
    
    **Power User Mode:**
    
    - Multiple simultaneous studies
    - Custom databases
    - API integration
    - Automated reporting
    
    Documentation soon...

## 💡 Tips for Success

!!! success "Best Practices"
    
    **For Accurate Data:**

    - Ensure good lighting (avoid backlighting)
    - Ask participants to keep their head relatively still
    - Test your calibration process first
    
    **For Better Studies:**

    - Keep tasks clear and specific
    - Don't have too many tasks
    - Pilot test with 2-3 people first
    - Provide clear instructions to participants

!!! warning "Common Gotchas"
    
    - **Calibration skipped?** Data quality suffers. Always calibrate!
    - **Poor lighting?** Tracking accuracy drops
    - **Too many browser tabs?** Close them for better performance
    - **Mobile devices?** Eye-tracking works best on desktop/laptop


## 🎯 Challenge: Run a Real Study!

Ready for the real deal?

1. **Design a meaningful study** - What do you want to learn?
2. **Recruit 5-10 participants** - Friends, colleagues, or users
3. **Collect real data** - Run your study!
4. **Analyze and share** - What did you discover?

Share your results with the community — we'd love to see what you learn! 🌟

---

**Feeling confident?** → [Learn about all features](overview.md)

**Want to go deeper?** → [Advanced configuration](configuration.md)
