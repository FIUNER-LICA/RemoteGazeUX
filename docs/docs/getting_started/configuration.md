# Configuration Guide

!!! tip "Customize Everything"
    RemoteGazeUX is designed to adapt to YOUR research needs. This guide shows you how to make it yours.

## 🎛️ Configuration Methods

You have two ways to configure RemoteGazeUX:

=== "🖥️ GUI (Recommended)"

    **Visual, friendly, no-code solution**

    You can open it when asked to modify the configuration with 

    ```bash
    python run.py
    ```

    Or with:

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
    "url_path": "https://google.com",
    "img_path": "null",
    "port": "5001"
}
```

**Available Options:**

| Setting | Description | Example |
|---------|-------------|---------|
| `url_path` | URL to a prototipe | "https://google.com" |
| `img_path` | Path to a static image | "/home/admin/example_image.png" |
| `port` | In which port it should run  | 8000 |


!!! example "Multiple Prototype Types"
    
    **Figma Prototype:**
    ```json
    {
      "url_path": "https://www.figma.com/proto/abc123/MyDesign",
      "img_path": "null"
    }
    ```
    
    **Static Image:**
    ```json
    {
      "url_path": "null",
      "img_path": "/home/admin/example_image.png"
    }
    ```
    
    **Live Website:**
    ```json
    {
      "url_path": "https://your-staging-site.com",
      "img_path": "null"
    }
    ```

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
    Invalid JSON will prevent the application from starting. Use a JSON validator!s

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

