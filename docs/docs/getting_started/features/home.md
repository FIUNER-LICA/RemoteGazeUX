# Participant Registration

!!! info "The Gateway to Your Study"
    This is the first thing participants see. Make it count!

## 🎯 Overview

The **Home Page** (accessible at `/`) is your study's front door. It's where participants:

1. Learn about the study
2. Provide demographic information
3. Give consent
4. Begin the tracking session

A well-designed entry page leads to better data quality and higher completion rates!

## 🌟 Features

### Clean, Professional Interface

First impressions matter. The home page features:

- **Welcome Message** - Explain what participants will do
- **Time Estimate** - Set expectations ("~10 minutes")
- **Privacy Notice** - Build trust with transparency
- **Simple Form** - Quick, non-intimidating registration

### Customizable Form Fields

Collect exactly the demographic data you need:

**Standard Fields:**
- 👤 Name / ID
- 🎂 Age
- ⚧ Gender
- 🌍 Location
- 💻 Device Information (auto-detected)

**Custom Fields:**
- Add your own questions
- Multiple field types (text, select, radio, checkbox)
- Required or optional
- Validation rules

!!! example "Custom Questions"
    ```json
    {
      "name": "web_experience",
      "label": "How often do you shop online?",
      "type": "select",
      "options": ["Daily", "Weekly", "Monthly", "Rarely"],
      "required": true
    }
    ```

### Smart Validation

Prevent bad data before it starts:

- ✅ Required field checking
- ✅ Format validation (email, age ranges)
- ✅ Real-time error messages
- ✅ Prevent duplicate submissions

### Consent Management

**GDPR-compliant consent tracking:**

- Clear explanation of data collection
- Explicit consent checkbox
- Link to privacy policy
- Timestamp of consent
- Option to withdraw

!!! warning "Legal Compliance"
    Always obtain informed consent before collecting data, especially for research involving human subjects.

## 🎨 Customization

### Branding

Make it yours:

```json
{
  "branding": {
    "logo_url": "/assets/my-logo.png",
    "study_title": "Navigation Usability Study",
    "welcome_message": "Help us improve our website!",
    "institution": "University of Example",
    "researcher_name": "Dr. Jane Smith"
  }
}
```

### Visual Design

Customize colors and styling:

```css
/* Custom CSS */
.entry-form {
  --primary-color: #3498db;
  --secondary-color: #2ecc71;
  --font-family: 'Roboto', sans-serif;
}
```

### Languages

Support international participants:

```json
{
  "language": "es",
  "text": {
    "welcome_title": "Bienvenido al Estudio",
    "start_button": "Comenzar",
    "required_field": "Campo requerido"
  }
}
```

## 📋 Form Configuration

### Example: Minimal Form

Just the essentials:

```json
{
  "participant_form": {
    "fields": [
      {
        "name": "participant_id",
        "label": "Participant ID",
        "type": "text",
        "required": true,
        "placeholder": "e.g., P001"
      }
    ]
  }
}
```

### Example: Comprehensive Form

Detailed demographics:

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
        "name": "email",
        "label": "Email Address",
        "type": "email",
        "required": true,
        "validation": "email"
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
        "options": ["Male", "Female", "Non-binary", "Prefer not to say"],
        "required": false
      },
      {
        "name": "education",
        "label": "Highest Education",
        "type": "select",
        "options": ["High School", "Bachelor's", "Master's", "PhD"],
        "required": true
      },
      {
        "name": "experience",
        "label": "Tech Experience",
        "type": "radio",
        "options": ["Beginner", "Intermediate", "Advanced"],
        "required": true
      },
      {
        "name": "consent",
        "label": "I consent to participate in this study",
        "type": "checkbox",
        "required": true
      }
    ]
  }
}
```

## 🔄 User Flow

### Step-by-Step Process

1. **Landing** 🌐
   - Participant visits the home URL
   - Sees welcome message and study description

2. **Reading Information** 📖
   - Reviews what the study involves
   - Understands time commitment
   - Reads privacy information

3. **Filling Form** ✍️
   - Enters required information
   - Sees real-time validation
   - Corrects any errors

4. **Consent** ✅
   - Checks consent box
   - Acknowledges data collection

5. **Submit** 🚀
   - Clicks "Begin Study"
   - Redirected to calibration page
   - Study session starts

### Visual Flow

```
┌─────────────────┐
│   Visit Home    │
│   Page (/)      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Read Study     │
│  Information    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Fill Out Form  │
│  (Demographics) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Give Consent   │
│  (Required)     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Submit Form    │
│  Begin Study    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Redirect to    │
│  Calibration    │
└─────────────────┘
```

## 💡 Best Practices

### Form Design

!!! success "Do's"
    - ✅ Keep it short (5-10 fields maximum)
    - ✅ Only ask for necessary information
    - ✅ Use clear, simple language
    - ✅ Provide helpful placeholders
    - ✅ Show progress or time estimate
    - ✅ Make "Start" button prominent

!!! failure "Don'ts"
    - ❌ Ask for sensitive info without reason
    - ❌ Use technical jargon
    - ❌ Make every field required
    - ❌ Use tiny text or confusing layouts
    - ❌ Hide important information

### Privacy & Ethics

- **Be Transparent** - Explain exactly what you'll collect
- **Minimize Data** - Only collect what you need
- **Secure Storage** - Protect participant information
- **Allow Withdrawal** - Let participants quit anytime
- **Provide Contact** - Offer researcher contact info

### Conversion Optimization

Increase completion rates:

1. **Clear Value Prop** - Why should they participate?
2. **Time Estimate** - "Only 10 minutes!"
3. **Incentive Display** - Show compensation clearly
4. **Trust Signals** - University logos, ethics approval
5. **Progress Indicator** - "Step 1 of 5"

## 🎯 Advanced Features

### Multi-Study Selection

Run multiple studies? Let participants choose:

```json
{
  "studies": [
    {
      "id": "study-1",
      "name": "Mobile App Navigation",
      "description": "Test our new app design",
      "duration": "10 minutes",
      "incentive": "$5 gift card"
    },
    {
      "id": "study-2",
      "name": "Website Redesign",
      "description": "Help improve our homepage",
      "duration": "15 minutes",
      "incentive": "$7 gift card"
    }
  ]
}
```

Participants see a study selector before the form!

### Conditional Fields

Show fields based on previous answers:

```json
{
  "name": "has_glasses",
  "label": "Do you wear glasses?",
  "type": "radio",
  "options": ["Yes", "No"]
},
{
  "name": "glasses_type",
  "label": "What type?",
  "type": "select",
  "options": ["Reading", "Distance", "Bifocals"],
  "show_if": {
    "field": "has_glasses",
    "value": "Yes"
  }
}
```

### Pre-filled Forms

For recruited participants:

```
https://your-study.com/?pid=P001&age=25&gender=Male
```

Form auto-fills from URL parameters!

### Screening Questions

Filter participants before they start:

```json
{
  "screening": {
    "enabled": true,
    "questions": [
      {
        "question": "Are you 18 years or older?",
        "required_answer": "Yes",
        "rejection_message": "Sorry, this study requires participants 18+"
      }
    ]
  }
}
```

## 📊 Data Collected

What gets stored:

| Field | Description | Example |
|-------|-------------|---------|
| `participant_id` | Unique identifier | `P001` or auto-generated UUID |
| `timestamp` | Registration time | `2024-11-04 14:32:15` |
| `demographic_data` | Form responses | `{"age": 25, "gender": "Male"}` |
| `consent` | Consent status | `true` |
| `study_id` | Which study | `navigation-study-1` |
| `ip_address` | IP (optional) | `192.168.1.1` or anonymized |
| `user_agent` | Browser info | Auto-detected |

## 🔧 Configuration Guide

### Basic Setup

1. **Edit config file:**
   ```bash
   python src/config.py
   ```

2. **Set study information:**
   - Study name
   - Description
   - Time estimate

3. **Configure form fields:**
   - Add/remove fields
   - Set required vs optional
   - Add validation rules

4. **Customize appearance:**
   - Upload logo
   - Set colors
   - Add custom CSS

5. **Save and restart:**
   ```bash
   python run.py
   ```

### Testing Your Form

Before launching:

1. **Test all fields** - Fill out completely
2. **Test validation** - Try invalid data
3. **Test on different devices** - Desktop, laptop, tablet
4. **Test different browsers** - Chrome, Firefox, Edge
5. **Test slow connections** - Ensure it loads fast

## 🆘 Troubleshooting

**Form not appearing?**
- Check `config.json` is valid JSON
- Verify server is running
- Check browser console for errors

**Fields not saving?**
- Check database connection
- Verify field names are unique
- Check for validation errors

**Consent not working?**
- Ensure checkbox is required
- Check consent field in config
- Verify database schema

---

**Next Step:** [Eye Tracking Process →](gaze_tracking.md)

**Back to:** [Features Overview →](../overview.md)