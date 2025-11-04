# Results & Analytics

!!! success "Where Data Becomes Insights"
    This is where the magic happens! Transform raw eye-tracking data into beautiful, actionable insights.

## 🎯 Overview

The **Results Page** (`/resultados?id={participant_id}`) is where you visualize and analyze individual participant sessions:

- 🔥 **Heatmaps** - See attention hotspots
- 👁️ **Gaze Plots** - Follow the eye's journey
- 🖱️ **Mouse Trails** - Track interaction patterns
- 📊 **Analytics** - Quantitative metrics
- 📥 **Exports** - Download for deeper analysis

**This is your "wow" moment** - the visual proof of what users actually see!

## 🔥 Heatmaps

### What is a Heatmap?

A heatmap shows **where people looked most** using color:

- 🔴 **Red/Orange** - High attention (looked here a LOT)
- 🟡 **Yellow** - Moderate attention
- 🟢 **Green/Blue** - Low attention
- ⚫ **No color** - Never looked here (blind spots!)

### The Power of Heatmaps

**See at a glance:**
```
┌───────────────────────────────────┐
│  🔥🔥🔥           🔴              │  ← Header gets attention
│                                   │
│  ████ Logo                        │  ← Logo is a hotspot!
│                                   │
│  🔴🟡 Navigation Menu              │  ← Menu scanned
│                                   │
│  ────────────────────────────     │
│                                   │
│  🟢 Hero Image                    │  ← Image mostly ignored
│  🟢                               │
│                                   │
│  🔴🔴🔴 "Get Started" Button      │  ← CTA attracts eyes!
│                                   │
│  🔵🔵 Footer                       │  ← Footer barely seen
└───────────────────────────────────┘
```

**Insights you can derive:**
- ✅ Is the CTA button visible?
- ✅ Do users see important information?
- ✅ Are there unexpected blind spots?
- ✅ Does the visual hierarchy work?

### Customization Options

#### Intensity Settings

Adjust heatmap appearance:

```json
{
  "heatmap": {
    "radius": 50,           // Blur radius (pixels)
    "max_opacity": 0.8,     // 0-1, transparency
    "gradient": {
      "0.0": "blue",
      "0.5": "yellow",
      "1.0": "red"
    }
  }
}
```

**Visual comparison:**

=== "Small Radius (25px)"
    
    **More precise, less smooth**
    
    Shows exact fixation points clearly
    
    Best for: Detailed analysis, text reading

=== "Medium Radius (50px)"
    
    **Balanced (recommended)**
    
    Good mix of precision and visibility
    
    Best for: General usability testing

=== "Large Radius (100px)"
    
    **Smooth, general patterns**
    
    Shows overall attention distribution
    
    Best for: Presentations, high-level insights

#### Color Schemes

Choose different color palettes:

**Classic (Red-Yellow-Blue):**
```
Cold ──────────────────► Hot
🔵 🟦 🟩 🟨 🟧 🟥
```

**Grayscale:**
```
Light ─────────────────► Dark
⚪ ⚫
```

**Custom:**
```json
{
  "gradient": {
    "0.0": "#00ff00",  // Green
    "0.5": "#ffff00",  // Yellow
    "1.0": "#ff0000"   // Red
  }
}
```

### Aggregate Heatmaps

**Compare multiple participants:**

=== "Individual"
    
    Single participant's attention
    
    ```
    Participant P001
    🔴🔴🔴  [Button Area]
    ```

=== "Averaged (n=10)"
    
    Average across 10 participants
    
    ```
    Average of 10 participants
    🔴🔴🟡  [Button Area]
    ```

=== "Comparison"
    
    Compare two groups
    
    ```
    Group A         vs        Group B
    🔴🔴🔴                     🟡🟡🔴
    ```

### Task-Specific Heatmaps

Filter by individual tasks:

```
Task 1: Find Login Button
┌──────────────────────┐
│  🔴🔴🔴  [Login]      │  ← Focused here!
│  🟢🟢    [Signup]     │
└──────────────────────┘

Task 2: Find Pricing
┌──────────────────────┐
│  🟢🟢    [Login]      │
│  🔴🔴🔴  [Pricing]    │  ← Then looked here!
└──────────────────────┘
```

## 👁️ Gaze Plots

### What is a Gaze Plot?

A gaze plot shows **the order and duration** of eye fixations:

```
       ③ (500ms)
         ↗
    ①  ↗
  (300ms) 
    ↓
    ② (750ms) → ④ (200ms) → ⑤ (1200ms)
```

**Each circle represents:**
- **Number** - Order of fixation (1st, 2nd, 3rd...)
- **Size** - Duration of fixation (bigger = longer)
- **Lines** - Saccades (rapid eye movements between fixations)

### Reading Gaze Plots

**Example analysis:**

```
Page with Navigation Menu
┌─────────────────────────────────┐
│  Logo  │ ① Home  ② About  ③ Contact
│        │   (250ms) (180ms) (320ms)
│        │      ↓       ↓       ↓
│        │      └───────┴───────┘
│                                │
│  ⑤ Hero Image                  │
│   (2000ms)                     │
│     ↑                          │
│     └──────────────────────────┘
│                     ↑
│  ④ "Get Started"    │
│     (450ms)         │
└─────────────────────┘
```

**What this tells us:**
1. User scanned navigation left-to-right ✅
2. Spent longest on hero image (2 seconds)
3. Button caught attention before hero
4. Quick scan of nav items (< 400ms each)

### Visualization Options

**Standard Gaze Plot:**
- Circles proportional to duration
- Numbers show sequence
- Lines show saccades

**Simplified Gaze Plot:**
- Just circles and numbers
- No connecting lines
- Cleaner for presentations

**Animated Replay:**
- Watch gaze move in real-time
- See exactly what participant did
- Great for understanding behavior

## 🖱️ Mouse Tracking

### Movement Trails

See where the mouse went:

```
┌─────────────────────────────────┐
│                   ╭─╮            │
│         ╭────────╯ ╰─╮          │
│        ╭╯            ╰╮         │
│  Start●               ●Click    │
│        ╰╮            ╭╯         │
│         ╰────────╮╭──╯          │
│                  ╰╯             │
└─────────────────────────────────┘
```

**Color coding:**
- 🔵 **Blue** - Movement
- 🟢 **Green** - Hover
- 🔴 **Red** - Click
- ⚫ **Black** - Drag

### Click Maps

See where people clicked:

```
Element Click Heatmap
┌─────────────────────────────┐
│  [Login]  ●●●●●● 45 clicks  │  ← Most clicked!
│  [Signup] ●●     12 clicks  │
│  [About]  ●      3 clicks   │
│  [Help]          0 clicks   │  ← Never clicked
└─────────────────────────────┘
```

### Scroll Behavior

Track page scrolling:

```
Scroll Depth
 0%  ████████████████████  100% viewed
25%  ████████████████████  100% viewed
50%  ████████████░░░░░░░░   68% viewed
75%  ████░░░░░░░░░░░░░░░░   23% viewed
100% ██░░░░░░░░░░░░░░░░░░    8% viewed
     
     └── Fold line (~600px)
```

**Insights:**
- Most users saw above-the-fold content
- Only 8% scrolled to bottom
- Consider moving important info up!

## 📊 Quantitative Analytics

### Session Metrics

**Overall performance:**

```
╔══════════════════════════════════════╗
║  📊 Session Analytics - P001         ║
╟──────────────────────────────────────╢
║  Duration:              9m 15s       ║
║  Tasks Completed:       3/3 ✅       ║
║  Calibration Accuracy:  87%          ║
║                                      ║
║  Gaze Data Points:      33,450       ║
║  Average Fixation:      245ms        ║
║  Total Fixations:       127          ║
║  Total Saccades:        126          ║
║                                      ║
║  Mouse Clicks:          23           ║
║  Mouse Distance:        2,847 pixels ║
║  Scroll Events:         12           ║
╚══════════════════════════════════════╝
```

### Task-Level Analytics

**Performance per task:**

| Task | Description | Time | Fixations | Clicks | Success |
|------|-------------|------|-----------|--------|---------|
| 1 | Find login | 0:45 | 38 | 5 | ✅ |
| 2 | Locate pricing | 1:23 | 52 | 8 | ✅ |
| 3 | Find support | 0:58 | 37 | 10 | ✅ |

### Areas of Interest (AOI)

Define regions and measure attention:

```
╔══════════════════════════════════════╗
║  Areas of Interest                   ║
╟──────────────────────────────────────╢
║  Header Navigation                   ║
║  Time to First Fixation:    0.8s     ║
║  Total Fixation Time:       2.4s     ║
║  Fixation Count:            12       ║
║  Revisits:                  3        ║
║                                      ║
║  Hero Section                        ║
║  Time to First Fixation:    1.2s     ║
║  Total Fixation Time:       5.1s     ║
║  Fixation Count:            23       ║
║  Revisits:                  1        ║
║                                      ║
║  CTA Button                          ║
║  Time to First Fixation:    3.5s     ║
║  Total Fixation Time:       1.8s     ║
║  Fixation Count:            8        ║
║  Click Rate:                100%     ║
╚══════════════════════════════════════╝
```

### Comparative Metrics

**Compare to study average:**

```
Participant vs Average (n=45)

Duration:         9m 15s  vs  8m 34s  ⬆️ +7%
Task 1 Time:      0:45     vs  0:46    ✓ Similar
Task 2 Time:      1:23     vs  1:20    ✓ Similar
Fixations:        127      vs  115     ⬆️ +10%
Clicks:           23       vs  28      ⬇️ -18%
```

## 🎨 Visualization Gallery

### Side-by-Side Comparison

```
┌──────────────────┬──────────────────┐
│   Heatmap        │   Gaze Plot      │
│                  │                  │
│   🔥🔴🟡         │   ①②③④⑤         │
│   🟢🔵           │   ↓ ↗ ↘ →        │
│                  │                  │
└──────────────────┴──────────────────┘
```

### Overlay Mode

Heatmap + Gaze plot combined:

```
┌─────────────────────────────────┐
│  🔥🔥🔥  ①②③                    │
│    🔴    (fixations on hotspot) │
│  🟡🟢                            │
└─────────────────────────────────┘
```

### Time-Lapse View

See how attention changes over time:

```
0-3 seconds      3-6 seconds      6-9 seconds
🔴 Header        🟡 Header        🔵 Header
🟢 Content       🔴 Content       🔴 Content
🔵 Footer        🔵 Footer        🟢 Footer
```

## 📥 Export Options

### Static Images

**Download visualizations:**

=== "PNG (High-Res)"
    
    **Best for:** Presentations, papers
    
    - Resolution: 1920x1080 or higher
    - Transparent background option
    - Multiple formats (heatmap, gaze plot, etc.)

=== "SVG (Vector)"
    
    **Best for:** Publications, scaling
    
    - Infinite resolution
    - Editable in Illustrator/Inkscape
    - Perfect for figures

=== "PDF"
    
    **Best for:** Reports, printing
    
    - Multi-page reports
    - Includes all visualizations
    - Publication-ready

### Raw Data Export

**CSV format for analysis:**

```csv
timestamp,task_id,x,y,fixation_duration,element_id,event_type
1698765432.123,1,450,320,234,button_login,fixation
1698765432.357,1,455,325,189,button_login,fixation
1698765432.546,1,523,412,0,null,saccade
1698765432.789,1,520,410,312,link_pricing,fixation
```

**What you can do with it:**
- Statistical analysis (R, Python, SPSS)
- Custom visualizations
- Machine learning
- Academic publications

### Analysis Reports

**Auto-generated PDF reports:**

```
📄 Participant P001 - Analysis Report
├─ 1. Executive Summary
├─ 2. Session Overview
├─ 3. Heatmap Visualizations
├─ 4. Gaze Plot Analysis
├─ 5. Task Performance
├─ 6. Quantitative Metrics
├─ 7. Recommendations
└─ 8. Raw Data Summary
```

## 🔬 Advanced Analytics

### Attention Metrics

**Calculate advanced metrics:**

| Metric | Formula | Insight |
|--------|---------|---------|
| **Dwell Time** | Total fixation time in AOI | How long they looked |
| **Entry Time** | Time to first fixation | When they noticed it |
| **Fixation Rate** | Fixations per second | Visual complexity |
| **Return Rate** | Revisits / total visits | Importance/confusion |
| **Scan Pattern** | Sequence of fixations | How they explore |

### Statistical Analysis

**Built-in statistics:**

```python
# Fixation duration statistics
Mean:       245ms
Median:     220ms
Std Dev:    89ms
Min:        120ms
Max:        1,850ms
95th %ile:  450ms

# Click accuracy
Target hits:    18/23 (78%)
Near misses:    4/23 (17%)
Far clicks:     1/23 (4%)
```

### Predictive Insights

**AI-powered analysis (coming soon):**

- 🤖 Automatic AOI detection
- 📊 Engagement scoring
- 🎯 Element visibility prediction
- 💡 UX improvement suggestions

## 💡 Interpreting Results

### Common Patterns

!!! success "Good Signs"
    
    **✅ Clear Visual Hierarchy**
    - Important elements get attention first
    - Logical scan pattern (F-pattern, Z-pattern)
    - CTA buttons are hotspots
    
    **✅ Efficient Navigation**
    - Short time to find targets
    - Few revisits (unless expected)
    - Smooth, logical gaze path
    
    **✅ Engagement**
    - Long dwell time on content
    - Multiple fixations on important info
    - Complete page exploration

!!! warning "Red Flags"
    
    **❌ Visual Confusion**
    - Random, scattered fixations
    - Many short fixations (< 150ms)
    - High return rate to same areas
    
    **❌ Navigation Issues**
    - Long search times
    - Never find target element
    - Excessive scrolling
    
    **❌ Blind Spots**
    - Important elements never seen
    - Banner blindness
    - Information buried

### Best Practices

**For Reliable Insights:**

1. **Sample Size**
   - Minimum: 5-10 participants
   - Recommended: 15-30 participants
   - Trends emerge: 20+ participants

2. **Task Design**
   - Realistic scenarios
   - Clear success criteria
   - Appropriate difficulty

3. **Environment**
   - Consistent across participants
   - Good calibration
   - Minimal distractions

4. **Analysis**
   - Look for patterns, not outliers
   - Combine qualitative + quantitative
   - Compare to benchmarks

## 🎯 Use Cases

### A/B Testing

**Compare two designs:**

```
Design A                Design B
🔴🔴🔴 CTA             🟡🟡🔴 CTA
45% click rate          67% click rate
Time to fixate: 3.2s    Time to fixate: 1.8s

Winner: Design B ✅
```

### Usability Issues

**Identify problems:**

```
Issue: Users can't find the search bar

Evidence:
- Only 20% found it within 10 seconds
- Average 8 revisits to header
- Heatmap shows it's a cold spot

Recommendation: Make search more prominent
```

### Content Optimization

**What gets read:**

```
Headline:     🔴🔴🔴  92% viewed
Subheading:   🟡🟡🔴  78% viewed
Body text:    🟢🟢🟡  34% viewed
Fine print:   🔵🔵🔵   5% viewed

Action: Move important info up!
```

## 🔧 Configuration

### Visualization Settings

```json
{
  "visualizations": {
    "default_view": "heatmap",
    "show_prototype": true,
    "heatmap": {
      "radius": 50,
      "opacity": 0.8,
      "min_opacity": 0.1
    },
    "gaze_plot": {
      "show_numbers": true,
      "show_saccades": true,
      "fixation_size_multiplier": 5
    },
    "mouse_trail": {
      "show_path": true,
      "show_clicks": true,
      "fade_duration": 1000
    }
  }
}
```

### Export Settings

```json
{
  "export": {
    "image_format": "png",
    "image_resolution": "1920x1080",
    "csv_delimiter": ",",
    "include_metadata": true,
    "timestamp_format": "unix"
  }
}
```

## 🆘 Troubleshooting

**Heatmap not appearing?**
- Check if data was collected
- Verify participant completed session
- Try refreshing page
- Check browser console

**Gaze plot looks chaotic?**
- Normal for complex pages!
- Try filtering by task
- Check calibration accuracy
- Consider using heatmap instead

**Export failing?**
- Check file permissions
- Verify CSV generation
- Try smaller time range
- Check browser downloads folder

**Low data quality?**
- Review calibration accuracy
- Check lighting conditions
- Verify participant followed instructions
- Consider excluding session

---

## 🎉 You're a Pro!

You now know how to:

- ✅ Generate beautiful heatmaps
- ✅ Analyze gaze plots
- ✅ Track mouse interactions
- ✅ Export data for analysis
- ✅ Interpret results
- ✅ Make data-driven decisions

**Ready to change how you do UX research?** 🚀

---

**Back to:** [Features Overview →](../overview.md)

**See also:** [Managing Participants →](subjects.md)

**Need help?** [Troubleshooting Guide](../../troubleshooting.md)