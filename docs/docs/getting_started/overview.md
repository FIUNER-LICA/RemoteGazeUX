# Features Overview

!!! info "Everything You Need for Professional Eye-Tracking Research"
    RemoteGazeUX packs enterprise-level features into an easy-to-use, open-source package.

## 🎯 Core Features

### 👁️ Webcam-Based Eye Tracking

**No hardware required.** Just a standard webcam.

- **WebGazer.js Integration** - Research-grade eye tracking in the browser
- **Automatic Calibration** - Smart calibration process guides participants
- **Real-time Tracking** - See gaze points as they're recorded
- **High Frequency Sampling** - Up to 60 Hz data collection
- **Cross-browser Support** - Works in Chrome, Firefox, and Edge

!!! success "Proven Accuracy"
    WebGazer.js has been validated in hundreds of research studies. Typical accuracy: 50-100 pixels under good conditions.

### 🖱️ Mouse Tracking

**Complete interaction picture.** Track every click, move, and scroll.

- **Movement Tracking** - Full mouse path recording
- **Click Detection** - Capture all clicks with timestamps
- **Scroll Monitoring** - Track scroll behavior
- **Element Identification** - Know exactly what was clicked
- **Synchronized Data** - Mouse and gaze data perfectly aligned

### 📊 Powerful Data Collection

**Professional-grade data storage and export.**

- **SQLite Database** - Fast, reliable, zero-configuration
- **PostgreSQL/MySQL Support** - Scale to thousands of participants
- **Automatic Timestamps** - Every data point time-stamped
- **Task Segmentation** - Data organized by task
- **CSV Export** - Analysis-ready data files
- **Batch Downloads** - Export entire studies at once

### 🎨 Flexible Prototype Support

**Test anything that runs in a browser.**

=== "Figma Prototypes"
    
    **Most Popular Choice**
    
    - Direct Figma embed support
    - Interactive prototypes
    - Real user flows
    - No technical setup
    
    Perfect for: UX designers, product teams

=== "Static Images"
    
    **Simple and Fast**
    
    - Upload any image
    - PNG, JPG, SVG support
    - Quick A/B testing
    - No prototype needed
    
    Perfect for: Visual design testing, mockup validation

=== "Live Websites"
    
    **Real-World Testing**
    
    - Test production sites
    - Staging environments
    - Any URL
    - Full interactivity
    
    Perfect for: Website redesigns, usability audits

=== "Custom HTML"
    
    **Maximum Control**
    
    - Upload custom HTML
    - Include JavaScript
    - Full customization
    - Advanced interactions
    
    Perfect for: Researchers, developers

## 🌟 Advanced Features

### 📋 Task-Based Studies

Structure your research with clear tasks:

- **Multiple Tasks** - Define sequential or parallel tasks
- **Time Limits** - Set duration for each task
- **Task Instructions** - Clear guidance for participants
- **Success Tracking** - Detect task completion automatically
- **Skip Logic** - Conditional task flows

### 📈 Beautiful Visualizations

**Publication-ready graphics, automatically generated.**

#### Heatmaps
See attention patterns at a glance:
- **Color-coded intensity** - Red = high attention, blue = low
- **Customizable radius** - Adjust blur for clarity
- **Overlay on prototype** - Direct visual feedback
- **High resolution** - Perfect for presentations

#### Gaze Plots
Follow the eye's journey:
- **Sequential path** - Numbered fixation points
- **Saccade lines** - See eye movements between fixations
- **Temporal information** - Understand viewing order
- **Fixation duration** - Size indicates time spent

#### Mouse Trails
Understand interaction patterns:
- **Movement paths** - Complete mouse journey
- **Click markers** - Where and when clicks occurred
- **Scroll indicators** - Page navigation patterns
- **Hover detection** - Interest without commitment

### 👥 Multi-User Management

**Built for teams.**

- **User Roles** - Admin, researcher, viewer
- **Authentication** - Secure login system
- **Session Management** - Track who's accessing data
- **Activity Logs** - Audit trail of all actions

### 🔒 Privacy & Security

**Your data stays yours.**

- **Self-Hosted** - Complete data control
- **Encrypted Storage** - Secure database
- **GDPR Ready** - Compliant data handling
- **Anonymization** - Optional participant anonymization
- **Consent Management** - Built-in consent tracking

### 🌐 Remote Testing

**Test participants anywhere in the world.**

- **Share a Link** - No installation for participants
- **Cross-Platform** - Windows, Mac, Linux
- **Mobile Support** - Desktop and laptop tested
- **Asynchronous** - Participants complete on their schedule
- **Automatic Storage** - Data saved immediately

### 📊 Study Management

**Organize complex research projects.**

- **Multiple Studies** - Run many studies simultaneously
- **Study Comparison** - Compare results across studies
- **Participant Filtering** - Slice data by demographics
- **Export Templates** - Standardized data formats
- **Batch Operations** - Manage multiple participants

## 🎓 Research-Grade Features

### Statistical Exports

**Ready for serious analysis.**

```csv
participant_id, task_id, timestamp, x, y, fixation_duration, element_id
P001, T01, 1698765432.123, 450, 320, 234, button_login
P001, T01, 1698765432.357, 455, 325, 189, button_login
...
```

Includes:
- Participant identifiers
- Task segmentation
- Precise timestamps (millisecond accuracy)
- Screen coordinates
- Fixation detection
- Element identification

### Reproducible Methodology

**Science-ready research.**

- **Version Control** - Track configuration changes
- **Standardized Calibration** - Consistent across participants
- **Documented Procedures** - Export study protocols
- **Random Assignment** - Built-in randomization for A/B tests

## 🚀 Performance Features

### Optimized Data Collection

**Fast and efficient.**

- **60 Hz Sampling** - Smooth, detailed tracking
- **Efficient Storage** - Compressed data formats
- **Background Processing** - No lag for participants
- **Automatic Cleanup** - Manage storage automatically

### Scalability

**From small pilots to large studies.**

- **Concurrent Participants** - Multiple simultaneous sessions
- **Large Datasets** - Handle thousands of participants
- **Database Optimization** - Indexed for fast queries
- **Export Streaming** - Handle huge files efficiently

## 🎨 Customization

### Appearance

- **Custom Branding** - Your logo, your colors
- **White Labeling** - Remove RemoteGazeUX branding
- **Custom CSS** - Complete visual control
- **Responsive Design** - Works on all screen sizes

### Functionality

- **API Access** - Programmatic control
- **Webhook Integration** - Real-time notifications
- **Custom Forms** - Collect any demographics
- **Plugin System** - Extend functionality

## 📱 Platform Support

### Browsers

✅ **Fully Supported:**
- Chrome 90+
- Firefox 88+
- Edge 90+

⚠️ **Partial Support:**
- Safari (limited webcam API)

### Operating Systems

✅ **Fully Supported:**
- Windows 10/11
- macOS 10.15+
- Linux (Ubuntu, Fedora, Debian)

### Devices

✅ **Recommended:**
- Desktop computers
- Laptops with webcams

⚠️ **Limited:**
- Tablets (calibration challenges)

❌ **Not Supported:**
- Smartphones (screen too small)

## 🎯 Use Cases

### UX Research

- **Usability Testing** - Find interface problems
- **Information Architecture** - Validate navigation
- **Visual Hierarchy** - Test design priorities
- **A/B Testing** - Compare design variants

### Marketing

- **Landing Page Optimization** - What catches attention?
- **Ad Testing** - Evaluate visual campaigns
- **Email Design** - Test newsletter layouts
- **Banner Design** - Optimize visual ads

### Academic Research

- **HCI Studies** - Human-computer interaction research
- **Visual Perception** - Study visual attention
- **Reading Patterns** - Text and layout research
- **User Behavior** - Interaction pattern analysis

### Product Development

- **Feature Discovery** - Are features findable?
- **Onboarding** - Test first-time user experience
- **Prototype Testing** - Validate before development
- **Competitive Analysis** - Study competitor interfaces

## 🔮 What's Coming

Planned features for future releases:

- **🎥 Screen Recording** - Video replay of sessions
- **🎤 Think-Aloud Protocol** - Audio recording support
- **📊 Advanced Analytics** - Built-in statistical analysis
- **🤖 AI Insights** - Automated attention analysis
- **📱 Mobile Support** - Eye tracking on tablets
- **☁️ Cloud Hosting** - Managed hosting option
- **🔗 CMS Integration** - WordPress, Webflow plugins
- **📧 Email Reports** - Automated study summaries

## 💡 Feature Highlights

!!! tip "Most Loved Features (User Feedback)"
    
    1. **One-Click Setup** - "Just works out of the box"
    2. **Beautiful Heatmaps** - "Client presentations are so easy now"
    3. **No Installation** - "Participants love that there's nothing to install"
    4. **CSV Export** - "Perfect for R and Python analysis"
    5. **Multiple Studies** - "Manage all my research in one place"

---

**Ready to explore specific features?** Choose a topic:

- [🏠 Participant Registration](features/home.md)
- [👁️ Eye Tracking Process](features/gaze_tracking.md)
- [👥 Managing Participants](features/subjects.md)
- [📊 Analyzing Results](features/results.md)
