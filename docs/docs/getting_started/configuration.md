# Configuration Guide

!!! tip "Customize Everything"
    RemoteGazeUX is designed to adapt to YOUR research needs. This guide shows you how to make it yours.

## 🎛️ Configuration Methods

You have two ways to configure RemoteGazeUX:

=== "🖥️ GUI (Recommended)"

    **Visual, friendly, no-code solution**
    
    ```bash
    python src/config.py
    ```
    
    Perfect for:
    - Quick changes
    - Non-technical team members
    - Visual learners
    - Initial setup

=== "📝 JSON Files"

    **Direct file editing for power users**
    
    Edit: `src/config/config.json` and `src/config/tasks.json`
    
    Perfect for:
    - Version control
    - Scripted deployments
    - Batch changes
    - Advanced users

Choose whatever works best for you! Both methods achieve the same result.

## 🔧 Core Configuration

### Study Settings

Configure the basics of your study:

```json
{
  "study_name": "Navigation Usability Study",
  "study_description": "Testing new header design",
  "prototype_url": "https://www.figma.com/proto/YOUR-LINK",
  "prototype_type": "figma"
}
```

**Available Options:**

| Setting | Description | Example |
|---------|-------------|---------|
| `study_name` | Name of your study | "Homepage Redesign Test" |
| `study_description` | Optional description | "Testing new hero section" |
| `prototype_url` | URL or path to your prototype | Figma link, image path, or website URL |
| `prototype_type` | Type of prototype | `"figma"`, `"image"`, `"website"` |

!!! example "Multiple Prototype Types"
    
    **Figma Prototype:**
    ```json
    {
      "prototype_url": "https://www.figma.com/proto/abc123/MyDesign",
      "prototype_type": "figma"
    }
    ```
    
    **Static Image:**
    ```json
    {
      "prototype_url": "/assets/prototype.png",
      "prototype_type": "image"
    }
    ```
    
    **Live Website:**
    ```json
    {
      "prototype_url": "https://your-staging-site.com",
      "prototype_type": "website"
    }
    ```

### Tracking Options

Control what data you collect:

```json
{
  "enable_gaze_tracking": true,
  "enable_mouse_tracking": true,
  "recording_frequency": 60,
  "enable_audio": false,
  "enable_screen_recording": false
}
```

**Configuration Options:**

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `enable_gaze_tracking` | Boolean | `true` | Track eye movements |
| `enable_mouse_tracking` | Boolean | `true` | Track mouse movements and clicks |
| `recording_frequency` | Number | `60` | Data points per second (Hz) |
| `enable_audio` | Boolean | `false` | Record audio (future feature) |

!!! warning "Performance Tip"
    Higher `recording_frequency` = more data but requires more processing power. 60 Hz is optimal for most studies.

### Calibration Settings

Fine-tune the calibration process:

```json
{
  "calibration_points": 9,
  "clicks_per_point": 5,
  "show_calibration_feedback": true,
  "validation_threshold": 0.85
}
```

**Calibration Options:**

| Setting | Range | Description |
|---------|-------|-------------|
| `calibration_points` | 5, 9, 13 | Number of calibration points (more = better accuracy) |
| `clicks_per_point` | 1-10 | Clicks required per point (5 is optimal) |
| `show_calibration_feedback` | Boolean | Show accuracy feedback to participant |
| `validation_threshold` | 0-1 | Minimum accuracy to pass calibration (0.85 = 85%) |

!!! tip "Calibration Best Practices"
    - **9 points** - Good balance of accuracy and time
    - **5 clicks** - Optimal for accuracy without fatigue
    - **Feedback ON** - Helps participants understand quality

## 📋 Task Configuration

Define tasks for your participants:

### Simple Tasks

Edit `src/config/tasks.json`:

```json
[
  {
    "id": 1,
    "description": "Find the login button",
    "duration": 30,
    "required": true
  },
  {
    "id": 2,
    "description": "Locate the pricing information",
    "duration": 45,
    "required": true
  },
  {
    "id": 3,
    "description": "Explore the features section",
    "duration": 60,
    "required": false
  }
]
```

**Task Properties:**

| Property | Type | Description |
|----------|------|-------------|
| `id` | Number | Unique identifier |
| `description` | String | What participants should do |
| `duration` | Number | Time limit in seconds |
| `required` | Boolean | Must complete to proceed |

### Advanced Task Features

Add complexity for sophisticated studies:

```json
{
  "id": 1,
  "description": "Find and click the 'Contact Us' button",
  "duration": 45,
  "required": true,
  "target_element": "button#contact",
  "success_criteria": {
    "type": "click",
    "element": "button#contact",
    "auto_advance": true
  },
  "hints": {
    "30": "The button is usually in the header or footer",
    "40": "Look at the top-right corner"
  }
}
```

!!! example "Task Ideas"
    
    **E-commerce:**
    - "Add the blue shirt to your cart"
    - "Find products under $50"
    - "Navigate to customer reviews"
    
    **SaaS Platform:**
    - "Create a new project"
    - "Find the pricing page"
    - "Locate the help documentation"
    
    **Information Site:**
    - "Find the contact information"
    - "Locate the hours of operation"
    - "Navigate to the about page"

## 👥 Participant Form

Customize what demographic data you collect:

### Default Form Fields

In `src/config/config.json`:

```json
{
  "participant_form": {
    "fields": [
      {
        "name": "name",
        "label": "Full Name",
        "type": "text",
        "required": true
      },
      {
        "name": "age",
        "label": "Age",
        "type": "number",
        "required": true,
        "min": 18,
        "max": 100
      },
      {
        "name": "gender",
        "label": "Gender",
        "type": "select",
        "options": ["Male", "Female", "Other", "Prefer not to say"],
        "required": false
      },
      {
        "name": "experience",
        "label": "How often do you use similar websites?",
        "type": "select",
        "options": ["Daily", "Weekly", "Monthly", "Rarely", "Never"],
        "required": true
      }
    ]
  }
}
```

### Custom Form Fields

Add domain-specific questions:

```json
{
  "name": "design_preference",
  "label": "Which design do you prefer?",
  "type": "radio",
  "options": ["Design A", "Design B", "No preference"],
  "required": true
},
{
  "name": "feedback",
  "label": "Any initial thoughts?",
  "type": "textarea",
  "required": false,
  "placeholder": "Optional feedback..."
}
```

**Available Field Types:**

| Type | Use Case | Example |
|------|----------|---------|
| `text` | Short text input | Name, email |
| `number` | Numeric input | Age, years of experience |
| `select` | Dropdown menu | Country, experience level |
| `radio` | Single choice | Gender, preference |
| `checkbox` | Multiple choices | Areas of interest |
| `textarea` | Long text | Comments, feedback |

## 🎨 Visual Customization

### Branding

Make it look like your brand:

```json
{
  "branding": {
    "logo_url": "/assets/logo.png",
    "primary_color": "#3498db",
    "secondary_color": "#2ecc71",
    "font_family": "Roboto, sans-serif",
    "custom_css": "/assets/custom.css"
  }
}
```

### Language & Text

Customize all text and language:

```json
{
  "text": {
    "welcome_title": "Welcome to Our UX Study!",
    "welcome_message": "Thank you for participating...",
    "calibration_instructions": "Please click each point 5 times",
    "task_prefix": "Task",
    "completion_message": "Thank you! Your responses have been recorded."
  }
}
```

## 🔐 Security & Privacy

### Authentication

Configure user access:

```json
{
  "authentication": {
    "require_login": true,
    "session_timeout": 3600,
    "max_login_attempts": 5,
    "password_min_length": 8
  }
}
```

### Data Privacy

```json
{
  "privacy": {
    "anonymize_data": false,
    "data_retention_days": 365,
    "allow_participant_deletion": true,
    "gdpr_compliant": true
  }
}
```

!!! warning "GDPR Compliance"
    If testing EU participants, ensure:
    - Participants consent to data collection
    - Data is anonymized when possible
    - Participants can request data deletion
    - You have a privacy policy

## 💾 Database Configuration

### SQLite (Default)

No configuration needed! Works out of the box.

```json
{
  "database": {
    "type": "sqlite",
    "path": "instance/data.db"
  }
}
```

### PostgreSQL (Production)

For larger studies:

```json
{
  "database": {
    "type": "postgresql",
    "host": "localhost",
    "port": 5432,
    "database": "remotegaze",
    "username": "postgres",
    "password": "your-password"
  }
}
```

### MySQL

Alternative production database:

```json
{
  "database": {
    "type": "mysql",
    "host": "localhost",
    "port": 3306,
    "database": "remotegaze",
    "username": "root",
    "password": "your-password"
  }
}
```

## 🌐 Network & Deployment

### Local Network Access

```json
{
  "server": {
    "host": "0.0.0.0",
    "port": 5000,
    "debug": false
  }
}
```

### HTTPS/SSL

```json
{
  "server": {
    "ssl_enabled": true,
    "ssl_cert": "cert.pem",
    "ssl_key": "key.pem"
  }
}
```

!!! tip "Webcam Access"
    Most modern browsers require HTTPS for webcam access. Use SSL in production!

## 🔄 Advanced Workflows

### Multiple Studies

Run multiple studies simultaneously:

```json
{
  "studies": [
    {
      "id": "study-1",
      "name": "Mobile Navigation",
      "prototype_url": "https://figma.com/proto/mobile",
      "active": true
    },
    {
      "id": "study-2",
      "name": "Desktop Header",
      "prototype_url": "https://figma.com/proto/desktop",
      "active": true
    }
  ]
}
```

Participants see a study selector on the entry page!

### A/B Testing

Configure variant testing:

```json
{
  "ab_testing": {
    "enabled": true,
    "variants": [
      {
        "id": "variant-a",
        "name": "Original Design",
        "prototype_url": "https://figma.com/proto/original",
        "weight": 50
      },
      {
        "id": "variant-b",
        "name": "New Design",
        "prototype_url": "https://figma.com/proto/new",
        "weight": 50
      }
    ],
    "random_assignment": true
  }
}
```

Participants are randomly assigned to variants!

## 🔍 Quality Control

### Attention Checks

Ensure participants are engaged:

```json
{
  "quality_control": {
    "attention_checks": true,
    "min_gaze_points": 100,
    "require_task_interaction": true,
    "exclude_incomplete": false
  }
}
```

## 📊 Export Configuration

Customize data exports:

```json
{
  "export": {
    "format": "csv",
    "include_mouse_data": true,
    "include_gaze_data": true,
    "include_metadata": true,
    "anonymize_exports": false,
    "timestamp_format": "ISO8601"
  }
}
```

## ⚡ Quick Config Templates

### Minimal Setup

Just the essentials:

```json
{
  "study_name": "Quick Test",
  "prototype_url": "https://your-link.com",
  "tasks": [
    {"id": 1, "description": "Explore freely", "duration": 60}
  ]
}
```

### Comprehensive Research Study

Full-featured configuration:

```json
{
  "study_name": "Comprehensive Navigation Study",
  "study_description": "Evaluating new information architecture",
  "prototype_url": "https://figma.com/proto/study",
  "enable_gaze_tracking": true,
  "enable_mouse_tracking": true,
  "calibration_points": 13,
  "tasks": [
    {
      "id": 1,
      "description": "Find product documentation",
      "duration": 45,
      "required": true,
      "target_element": "#docs-link"
    },
    {
      "id": 2,
      "description": "Locate pricing information",
      "duration": 30,
      "required": true
    },
    {
      "id": 3,
      "description": "Find customer support options",
      "duration": 45,
      "required": true
    }
  ],
  "participant_form": {
    "fields": [
      {"name": "name", "type": "text", "required": true},
      {"name": "age", "type": "number", "required": true},
      {"name": "experience", "type": "select", 
       "options": ["Beginner", "Intermediate", "Expert"],
       "required": true}
    ]
  }
}
```

## 🔄 Applying Configuration Changes

### Using the GUI

1. Open config GUI: `python src/config.py`
2. Make your changes
3. Click **Save**
4. Restart the application: `python run.py`

### Editing JSON Directly

1. Edit `src/config/config.json` and/or `src/config/tasks.json`
2. Save the files
3. Restart: `python run.py`

!!! warning "Validation"
    Invalid JSON will prevent the application from starting. Use a JSON validator!

## 🆘 Troubleshooting

**Configuration not loading?**
- Check JSON syntax (no trailing commas!)
- Ensure required fields are present
- Check file permissions

**Tasks not appearing?**
- Verify `tasks.json` is valid JSON
- Ensure task IDs are unique
- Check task `required` field

**Prototype not loading?**
- Verify URL is accessible
- Check prototype type matches URL
- Ensure CORS settings allow embedding

---

**Ready to run your configured study?** → [Quick Start Guide](quickstart.md)

**Need help with features?** → [User Guide](../user_guide/overview.md)
