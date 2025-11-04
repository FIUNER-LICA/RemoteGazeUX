# Frequently Asked Questions (FAQ)

!!! question "Got Questions?"
    Here are answers to the most common questions about RemoteGazeUX!

## 🚀 Getting Started

### How much does RemoteGazeUX cost?

**RemoteGazeUX is completely free and open-source!** 

- No licensing fees
- No subscription costs
- No hidden charges
- Use it for commercial or academic purposes (GPL-3.0 license)

### What equipment do I need?

**Minimal requirements:**

For the **server** (running RemoteGazeUX):
- Computer with Python 3.8+
- Any operating system (Windows, Mac, Linux)

For **participants**:
- Webcam (built-in or external)
- Modern browser (Chrome, Firefox, or Edge)
- Internet connection

**That's it!** No eye-tracking hardware needed.

### How accurate is webcam-based eye tracking?

**Typical accuracy: 50-100 pixels** (about 1-2 cm on a standard monitor)

**Factors affecting accuracy:**
- ✅ Good calibration = better accuracy
- ✅ Good lighting = better accuracy
- ✅ Participant staying still = better accuracy
- ✅ HD webcam = better accuracy

**Is this accurate enough?**
- ✅ YES for: Identifying which elements get attention, general gaze patterns, heatmaps
- ⚠️ LIMITED for: Reading exact words, precise pixel-level accuracy
- ❌ NOT for: Medical diagnosis, foveated rendering

For UX research and usability testing, this accuracy is excellent!

### Can I test on mobile devices?

**Currently: Desktop/laptop only**

- ✅ **Works:** Desktop computers and laptops
- ⚠️ **Limited:** Tablets (calibration challenges)
- ❌ **Not supported:** Smartphones

Mobile eye tracking is on our roadmap! 🚀

## 📊 Studies & Data

### How many participants can I test?

**Unlimited!** RemoteGazeUX scales from small pilots to large studies.

**Tested configurations:**
- Small study: 5-10 participants ✅
- Medium study: 50-100 participants ✅
- Large study: 500+ participants ✅

**Database recommendations:**
- < 100 participants: SQLite (default) ✅
- 100-1000 participants: PostgreSQL ✅
- 1000+ participants: PostgreSQL with optimization ✅

### Can I run multiple studies simultaneously?

**Yes!** RemoteGazeUX supports multiple concurrent studies.

Each study gets:
- Own participant pool
- Separate data storage
- Individual configuration
- Dedicated results page

Perfect for A/B testing or managing multiple projects!

### How long can a session be?

**Recommended: 10-20 minutes maximum**

**Technical limits:**
- Maximum: No hard limit
- Practical: Keep under 30 minutes

**Why shorter is better:**
- Participant fatigue affects data quality
- Eye tracking accuracy degrades over time
- Higher completion rates
- Better participant experience

**Pro tip:** Break long studies into multiple shorter sessions!

### What happens if a participant quits mid-session?

**Their data is preserved!**

- All data up to quit point is saved
- Marked as "incomplete" in dashboard
- Still viewable and downloadable
- Can exclude from analysis if needed

**Data integrity:** Even incomplete sessions provide valuable insights!

### Can participants pause and resume?

**Currently: No**

Sessions are continuous. Once started, participants should complete without pausing.

**Workaround:**
- Design shorter sessions
- Break into multiple separate studies
- Communicate time commitment upfront

Session pause/resume is on our roadmap!

## 🔧 Technical Questions

### What browsers are supported?

**Fully supported:**
- ✅ Chrome 90+ (Recommended)
- ✅ Firefox 88+
- ✅ Edge 90+

**Limited support:**
- ⚠️ Safari 14+ (webcam API limitations)

**Not supported:**
- ❌ Internet Explorer
- ❌ Opera Mini
- ❌ Mobile browsers

**Recommendation:** Ask participants to use Chrome for best results.

### Do I need HTTPS?

**For local testing:** No, HTTP works fine

**For remote participants:** Yes, HTTPS required

**Why?** Modern browsers require HTTPS for:
- Webcam access
- Microphone access (if used)
- Secure data transmission

**Good news:** RemoteGazeUX includes self-signed certificates for easy HTTPS testing!

### Can I use my own database?

**Yes!** Multiple options:

**Default: SQLite**
- Zero configuration
- Perfect for most uses
- File-based (portable)

**Upgrade options:**
- PostgreSQL (recommended for 100+ participants)
- MySQL/MariaDB
- Any SQLAlchemy-compatible database

Configuration is simple - just edit the config file!

### Can I customize the look and feel?

**Absolutely!** RemoteGazeUX is highly customizable:

**Easy customization:**
- Logo and branding
- Colors and fonts
- Text and language
- Form fields

**Advanced customization:**
- Custom CSS
- Template modifications
- Complete UI overhaul

**All through configuration - no coding required** (unless you want to)!

## 🔐 Privacy & Security

### Is participant data secure?

**RemoteGazeUX is self-hosted** - you control all data!

**Security features:**
- Self-hosted (data stays on your server)
- Password-protected admin access
- HTTPS/SSL support
- Optional anonymization
- No third-party data sharing

**Important:** You're responsible for:
- Server security
- Database protection
- Proper authentication
- Following data protection laws

### Is RemoteGazeUX GDPR compliant?

**RemoteGazeUX provides tools for GDPR compliance:**

✅ **Consent management** - Built-in consent tracking
✅ **Data minimization** - Collect only what you need
✅ **Right to deletion** - Easy participant removal
✅ **Data portability** - CSV exports
✅ **Anonymization** - Remove PII options

**However:** GDPR compliance depends on how YOU use the tool.

**You must:**
- Obtain informed consent
- Have a privacy policy
- Implement proper data handling
- Respect participant rights

**We provide the tools - you ensure compliance!**

### What data is collected?

**Automatic collection:**
- Eye gaze coordinates (x, y)
- Timestamps (millisecond precision)
- Mouse movements and clicks
- Screen resolution
- Browser/OS info (user agent)

**Optional collection:**
- Demographics (you configure)
- Task responses
- Custom form fields
- IP addresses (can disable)

**NOT collected:**
- Webcam video/images
- Audio
- Personal files
- Browsing history outside study

**Gaze data stays in browser - only coordinates sent to server!**

### Can I share data with collaborators?

**Yes! Multiple options:**

**1. User accounts**
- Create accounts with different access levels
- Admin, researcher, viewer roles
- Password protection

**2. Data exports**
- Download CSV files
- Share via Dropbox, Drive, etc.
- Email to collaborators

**3. Database access**
- Direct database queries
- API integration (for developers)

**Best practice:** Use viewer accounts for collaborators who only need to see results.

## 📈 Results & Analysis

### What visualizations are included?

**Built-in visualizations:**
- 🔥 Heatmaps (attention distribution)
- 👁️ Gaze plots (fixation sequence)
- 🖱️ Click maps (interaction heatmaps)
- 📊 Task analytics (completion metrics)
- 📈 Aggregate statistics

**Export options:**
- High-res PNG images
- Vector SVG files
- PDF reports
- Raw CSV data

**All automatically generated - no manual work!**

### Can I export data for statistical analysis?

**Yes! Multiple export formats:**

**CSV (most common):**
```csv
participant_id,task_id,timestamp,x,y,fixation,element_id
P001,1,1698765432.123,450,320,true,button_login
```

**JSON (structured):**
```json
{
  "participant": {...},
  "gaze_data": [...],
  "mouse_data": [...]
}
```

**Perfect for:**
- R analysis
- Python (pandas, numpy)
- SPSS
- Excel
- Tableau

**All data is timestamped and structured for easy analysis!**

### How do I compare participants?

**Multiple comparison tools:**

**1. Aggregate heatmaps**
- Average across all participants
- Compare groups (e.g., age groups)
- Identify common patterns

**2. Task metrics**
- Average completion time
- Success rates
- Fixation counts

**3. CSV exports**
- Download all data
- Custom analysis in R/Python
- Statistical tests

**4. Built-in filters**
- Compare by demographics
- Filter by performance
- Segment by any variable

### Can I create custom visualizations?

**Yes! Two approaches:**

**1. Use raw data exports**
- Download CSV
- Import to your tool (Python, R, Tableau)
- Create any visualization you want

**2. Extend RemoteGazeUX (advanced)**
- Add custom visualization code
- Integrate with other libraries
- Contribute back to project!

**The data is yours - visualize it however you like!**

## 🎓 Research & Academic Use

### Can I use RemoteGazeUX for my research?

**Absolutely!** That's what it's designed for!

**Perfect for:**
- UX research studies
- HCI experiments  
- Psychology research
- Marketing studies
- Academic papers

**Already used in published research!**

### How do I cite RemoteGazeUX?

**For now, cite the underlying technology (WebGazer.js):**

```bibtex
@inproceedings{papoutsaki2016webgazer,
  title={WebGazer: Scalable Webcam Eye Tracking Using User Interactions},
  author={Papoutsaki, Alexandra and others},
  booktitle={IJCAI},
  year={2016}
}
```

**Also mention RemoteGazeUX in your methods:**

> "Data collection was performed using RemoteGazeUX 
> (https://github.com/justogm/RemoteGazeUX), an open-source 
> platform for remote eye-tracking studies."

**Academic citation coming soon!**

### Is the methodology scientifically valid?

**Yes!** WebGazer.js (our eye-tracking engine) has been:

- ✅ Validated in academic research
- ✅ Cited in 1000+ papers
- ✅ Published in top-tier conferences (IJCAI)
- ✅ Used in numerous studies

**RemoteGazeUX adds:**
- Standardized data collection
- Reproducible methodology
- Easy remote testing
- Publication-ready exports

**Use it with confidence in academic research!**

### Can I get ethics approval with RemoteGazeUX?

**Many researchers have!**

**What ethics boards typically want:**
- ✅ Informed consent process (built-in)
- ✅ Data security (self-hosted)
- ✅ Participant privacy (anonymization options)
- ✅ Right to withdraw (configurable)

**Tips for ethics approval:**
1. Explain webcam-based eye tracking
2. Show consent process
3. Demonstrate data security
4. Provide privacy policy
5. Show data deletion capability

**Need help?** Email us - we can provide documentation!

## 🤝 Support & Community

### Where do I get help?

**Multiple support channels:**

**1. Documentation**
- Comprehensive guides
- Step-by-step tutorials
- Troubleshooting section

**2. GitHub Issues**
- Report bugs
- Request features
- Ask questions

**3. Email support**
- justo.garcia@ingenieria.uner.edu.ar
- Usually respond within 48 hours

**4. Community** (coming soon)
- Discussion forum
- User group
- Slack channel

### How can I contribute?

**We love contributions!**

**Ways to help:**
- 🐛 Report bugs
- ✨ Suggest features
- 📝 Improve documentation
- 💻 Submit code
- 🌍 Translate interface
- 🎨 Design improvements
- 📢 Spread the word

**New to open source?** Start with documentation improvements!

**See:** [Contributing Guide](development/contributing.md)

### Is there commercial support?

**Currently:** Community support only

**Coming soon:**
- Commercial support packages
- Consulting services
- Custom development
- Training workshops
- Managed hosting

**Interested?** Email us to be notified when available!

## 🔮 Future Features

### What's on the roadmap?

**Planned features:**

**Short-term (next 3-6 months):**
- 🎥 Screen recording
- 📊 Advanced analytics
- 🌐 Multi-language interface
- 📱 Better mobile support

**Medium-term (6-12 months):**
- 🤖 AI-powered insights
- ☁️ Cloud hosting option
- 🔌 Third-party integrations
- 📧 Automated reports

**Long-term (12+ months):**
- 📱 Full mobile eye tracking
- 🎮 Gaming/VR support
- 🧠 Attention prediction
- 🌍 Global participant network

**Vote on features:** [GitHub Discussions](https://github.com/justogm/RemoteGazeUX/discussions)

### Will RemoteGazeUX always be free?

**Yes! The core will always be free and open-source.**

**Future monetization (maybe):**
- ☁️ Optional managed hosting (pay for convenience)
- 💼 Commercial support packages
- 🎓 Training and consulting
- 🚀 Premium features (enterprise only)

**Core promise:** Individual researchers and small teams will always have access to full functionality for free!

## 💡 Tips & Tricks

### How do I get the best data quality?

**Top tips:**

**1. Calibration is key**
- Don't rush calibration
- Ensure good lighting
- Have participants follow instructions carefully

**2. Participant instructions**
- Explain the process clearly
- Set time expectations
- Ensure quiet environment

**3. Task design**
- Keep tasks realistic
- Clear success criteria
- Appropriate difficulty

**4. Technical setup**
- Test everything first
- Use Chrome browser
- Check internet speed

**5. Pilot testing**
- Run 3-5 pilot participants
- Fix issues before full launch
- Iterate on instructions

### What sample size do I need?

**Depends on your goal:**

**Quick feedback:** 5-8 participants
- Find major usability issues
- Identify obvious problems
- Quick iteration

**Usability testing:** 15-20 participants
- Reliable patterns emerge
- Statistical confidence
- Publication-worthy

**Research study:** 30+ participants
- Strong statistical power
- Demographic subgroups
- Academic rigor

**A/B testing:** 50+ per variant
- Detect small differences
- Statistical significance
- Confident decisions

**Rule of thumb:** More is better, but 15-20 is the sweet spot for most UX studies!

---

## 🤔 Still Have Questions?

**Didn't find your answer?**

- 📖 [Check the full documentation](index.md)
- 🐛 [Ask on GitHub Issues](https://github.com/justogm/RemoteGazeUX/issues)
- 📧 [Email us](mailto:justo.garcia@ingenieria.uner.edu.ar)

**We're here to help!** 💙
