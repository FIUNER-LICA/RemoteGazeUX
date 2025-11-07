# Installation Guide

!!! tip "You'll be up and running in under 5 minutes!"
    RemoteGazeUX is designed for simplicity. No complex setup, no configuration headaches.

## 📋 Prerequisites

Before you begin, make sure you have:

- **Python 3.8 or higher** ([Download Python](https://www.python.org/downloads/))
- **Git** (optional, but recommended) ([Download Git](https://git-scm.com/downloads))
- **A webcam** (built-in or external)
- **A modern browser** (Chrome, Firefox, or Edge)

That's it! No expensive hardware, no special equipment.

---

## 🚀 Quick Installation

=== "Method 1: Git Clone (Recommended)"

    The fastest way to get started:

    ```bash
    # 1. Clone the repository
    git clone https://github.com/justogm/RemoteGazeUX.git
    
    # 2. Navigate to the folder
    cd RemoteGazeUX
    
    # 3. Run the application
    python run.py
    ```

    That's all! 🎉 The script will:
    
    - ✅ Automatically install all dependencies
    - ✅ Set up the database
    - ✅ Walk you through initial configuration
    - ✅ Start the web server

=== "Method 2: Download ZIP"

    Prefer not to use Git? No problem:

    1. **Download**: Go to the [repository page](https://github.com/justogm/RemoteGazeUX)
    2. **Extract**: Click the green "Code" button → "Download ZIP"
    3. **Unzip**: Extract the ZIP file to your preferred location
    4. **Run**: Open a terminal in the extracted folder and run:
    
    ```bash
    python run.py
    ```

---

## 🎯 First Run Setup

When you run `python run.py` for the first time, you'll see an interactive setup wizard:

### Step 1: Create Admin Account

```
🔐 Current users in database: 0
Do you want to create a new user? (y/n): y

============================================================
👥 CREATE NEW USER
============================================================

Username: admin
Password: 
Confirm password: 

✅ User 'admin' created successfully!
============================================================
```

!!! warning "Keep these credentials safe!"
    You'll need them to access participant data and results.

### Step 2: Configure Your Study

When the application detects that you set in the configuration an url that wasn't present in the database it will allow you to set a name and a description.

```
============================================================
📊 New configuration detected!
============================================================
Prototype URL: https://google.com

Enter a name for this study (or press Enter for auto-name): Google Sudy
Enter a description (optional): Study of Google UX
✅ Created new study: 'Google Sudy' (ID: 1)
============================================================
```

### Step 3: Launch! 🚀

---

## ✅ Verify Installation

Open your browser and navigate to the url shown at the end of the print. You should see the participant registration page!

!!! success "Installation Complete! 🎉"
    You're ready to run your first eye-tracking study!

## 🐛 Troubleshooting

### Port Already in Use?

If port is busy, you can change it with the configuration at the start of the run.

### Python Not Found?

Make sure Python is in your PATH. Try:

```bash
python3 run.py  # On macOS/Linux
py run.py       # On Windows
```

### Permission Errors?

On Linux/macOS, you might need:

```bash
chmod +x run.py
```

### Need Help?

- 📖 Check the [troubleshooting guide](../troubleshooting.md) 
TODO: fix troubleshooting link
- 🐛 [Open an issue](https://github.com/justogm/RemoteGazeUX/issues)
- 💬 Ask the community

## 🎓 Next Steps

Now that you're up and running:

1. 📚 Learn about [configuring studies](configuration.md)
2. 👀 Explore the [features](overview.md)
3. 🎯 Run your [first study](quickstart.md)

---

**Ready to start tracking?** → [Quick Start Guide](quickstart.md)
