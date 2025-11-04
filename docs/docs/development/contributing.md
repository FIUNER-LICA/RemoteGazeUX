# Contributing to RemoteGazeUX

!!! heart "Thank You!"
    First off, thank you for considering contributing to RemoteGazeUX! It's people like you that make open source amazing. 🌟

## 🌈 Ways to Contribute

Everyone can contribute to RemoteGazeUX, regardless of skill level!

### 🐛 Report Bugs

**Found a bug?** Help us squash it!

1. **Check** if it's already reported in [Issues](https://github.com/justogm/RemoteGazeUX/issues)
2. **Open a new issue** with the bug report template
3. **Include details:**
   - What you expected to happen
   - What actually happened
   - Steps to reproduce
   - Your environment (OS, Python version, browser)
   - Screenshots if relevant

**Good bug reports are gold!** They help us fix issues faster.

### 💡 Suggest Features

**Have an idea?** We want to hear it!

1. **Check** existing [feature requests](https://github.com/justogm/RemoteGazeUX/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
2. **Open a discussion** or issue
3. **Explain:**
   - What problem it solves
   - How you'd use it
   - Why it benefits the community

**All ideas welcome!** Even if we can't implement everything, your input shapes the roadmap.

### 📝 Improve Documentation

**Best first contribution!** No coding required.

**What you can do:**
- Fix typos and grammar
- Clarify confusing sections
- Add examples
- Write tutorials
- Create diagrams
- Translate to other languages

**Even small fixes help!** Documentation is never perfect.

### 💻 Code Contributions

**Ready to code?** Awesome!

**Good starting points:**
- [Good first issues](https://github.com/justogm/RemoteGazeUX/labels/good%20first%20issue)
- [Help wanted](https://github.com/justogm/RemoteGazeUX/labels/help%20wanted)
- Documentation improvements
- Test coverage

### 🎨 Design Improvements

**Make RemoteGazeUX beautiful!**

- UI/UX improvements
- Better icons
- Clearer layouts
- Accessibility enhancements
- Visual polish

### 🌍 Translations

**Help make RemoteGazeUX accessible globally!**

We'd love to support:
- Spanish
- French
- German
- Chinese
- Japanese
- Portuguese
- And more!

## 🚀 Getting Started

### 1. Fork & Clone

```bash
# Fork the repo on GitHub (click "Fork" button)

# Clone your fork
git clone https://github.com/YOUR-USERNAME/RemoteGazeUX.git
cd RemoteGazeUX

# Add upstream remote
git remote add upstream https://github.com/justogm/RemoteGazeUX.git
```

### 2. Set Up Development Environment

```bash
# Create virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies (including dev dependencies)
pip install -r requirements.txt
pip install -r requirements-dev.txt

# Run tests to verify setup
pytest
```

### 3. Create a Branch

```bash
# Fetch latest changes
git fetch upstream
git checkout main
git merge upstream/main

# Create feature branch
git checkout -b feature/amazing-feature
# or
git checkout -b fix/bug-description
```

**Branch naming:**
- `feature/feature-name` - New features
- `fix/bug-description` - Bug fixes
- `docs/what-changed` - Documentation
- `refactor/what-changed` - Code refactoring
- `test/what-added` - Test additions

### 4. Make Your Changes

**Follow these guidelines:**

#### Code Style

We use:
- **[Black](https://black.readthedocs.io/)** for Python formatting
- **[isort](https://pycqa.github.io/isort/)** for import sorting
- **[flake8](https://flake8.pycqa.org/)** for linting

```bash
# Format code
black .

# Sort imports
isort .

# Check linting
flake8 src tests
```

**Tip:** Set up pre-commit hooks:
```bash
pip install pre-commit
pre-commit install
```

#### Code Guidelines

```python
# Good: Clear, documented, tested
def calculate_fixation_duration(gaze_points, threshold=100):
    """Calculate duration of eye fixations.
    
    Args:
        gaze_points (list): List of gaze point dictionaries
        threshold (int): Min duration in ms to count as fixation
    
    Returns:
        float: Total fixation duration in seconds
    """
    # Implementation with clear variable names
    total_duration = 0
    for point in gaze_points:
        if point['duration'] >= threshold:
            total_duration += point['duration']
    return total_duration / 1000.0
```

**Follow:**
- Clear function and variable names
- Docstrings for all public functions
- Type hints where helpful
- Comments for complex logic
- DRY (Don't Repeat Yourself)

#### Testing

**All new features need tests!**

```python
# tests/test_analytics.py
import pytest
from src.analytics import calculate_fixation_duration

def test_calculate_fixation_duration():
    """Test fixation duration calculation."""
    gaze_points = [
        {'duration': 150},
        {'duration': 200},
        {'duration': 50},  # Below threshold
    ]
    
    result = calculate_fixation_duration(gaze_points, threshold=100)
    
    assert result == 0.35  # (150 + 200) / 1000
```

**Run tests:**
```bash
# All tests
pytest

# With coverage
pytest --cov=src tests/

# Specific test file
pytest tests/test_analytics.py

# Specific test
pytest tests/test_analytics.py::test_calculate_fixation_duration
```

### 5. Commit Your Changes

**Write good commit messages:**

```bash
# Good commit message format:
# <type>: <subject>
# 
# <body>
# 
# <footer>

git commit -m "feat: add fixation duration calculation

- Implement calculate_fixation_duration function
- Add support for custom duration thresholds
- Include comprehensive tests

Closes #123"
```

**Commit types:**
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation changes
- `style:` - Code style changes (formatting)
- `refactor:` - Code refactoring
- `test:` - Test additions or changes
- `chore:` - Maintenance tasks

### 6. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/amazing-feature

# Go to GitHub and create a Pull Request
```

**PR Guidelines:**

**Title:** Clear and descriptive
```
✅ "Add fixation duration calculation"
❌ "Update analytics"
```

**Description:** Use the template
```markdown
## Description
Adds a new function to calculate fixation durations from gaze data.

## Type of Change
- [x] New feature
- [ ] Bug fix
- [ ] Documentation update

## Testing
- [x] Unit tests added
- [x] Manual testing completed
- [x] All tests pass

## Related Issues
Closes #123

## Screenshots (if applicable)
![Fixation visualization](screenshot.png)
```

**Checklist:**
- [ ] Code follows style guidelines
- [ ] Self-reviewed the code
- [ ] Commented complex code
- [ ] Updated documentation
- [ ] Added tests
- [ ] All tests pass
- [ ] No breaking changes (or documented)

## 📋 Development Workflow

### Typical Workflow

```
1. Find/create issue → Discuss approach
2. Fork & clone → Set up environment
3. Create branch → Make changes
4. Test locally → Ensure quality
5. Commit → Push
6. Open PR → Request review
7. Address feedback → Update PR
8. Merge! → Celebrate 🎉
```

### Code Review Process

1. **Automated checks** run first (tests, linting)
2. **Maintainer reviews** your code
3. **Feedback provided** if needed
4. **You update** based on feedback
5. **Approval & merge** when ready

**Be patient!** Reviews may take a few days. We're volunteers too!

### After Your PR is Merged

1. **Celebrate!** 🎉 You're now a contributor!
2. **Update your fork:**
   ```bash
   git checkout main
   git pull upstream main
   git push origin main
   ```
3. **Delete feature branch:**
   ```bash
   git branch -d feature/amazing-feature
   git push origin --delete feature/amazing-feature
   ```
4. **Find your next contribution!**

## 🎯 Contribution Guidelines

### Do's ✅

- **Do** start with small contributions
- **Do** ask questions if unclear
- **Do** write tests for new features
- **Do** update documentation
- **Do** follow the code style
- **Do** be respectful and patient
- **Do** celebrate your contributions!

### Don'ts ❌

- **Don't** submit huge PRs without discussion
- **Don't** break existing functionality
- **Don't** ignore CI failures
- **Don't** commit generated files
- **Don't** copy code without attribution
- **Don't** be discouraged by feedback

## 🏆 Recognition

### Contributors Get

- 🌟 Listed in README and docs
- 🎉 Mentioned in release notes
- 💙 Eternal gratitude
- 📧 Direct line to maintainers
- 🚀 Impact on real research

### Significant Contributors May Get

- ✍️ Co-authorship on papers
- 🎤 Conference presentation opportunities
- 💼 Recommendation letters
- 🤝 Collaboration opportunities

## 📚 Resources

### Learning Resources

**New to Open Source?**
- [First Contributions](https://firstcontributions.github.io/)
- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)

**Python Development:**
- [Real Python Tutorials](https://realpython.com/)
- [Python Style Guide (PEP 8)](https://pep8.org/)
- [Writing Good Commit Messages](https://chris.beams.io/posts/git-commit/)

**Testing:**
- [Pytest Documentation](https://docs.pytest.org/)
- [Test-Driven Development](https://www.obeythetestinggoat.com/)

### Project Documentation

- [Architecture Overview](architecture.md)
- [API Documentation](../api_reference/)
- [Testing Guide](testing.md)

## 💬 Communication

### Where to Ask Questions

**General questions:**
- [GitHub Discussions](https://github.com/justogm/RemoteGazeUX/discussions)

**Specific to your PR:**
- Comment on the PR itself

**Private/sensitive:**
- Email: [justo.garcia@ingenieria.uner.edu.ar](mailto:justo.garcia@ingenieria.uner.edu.ar)

### Response Times

- **GitHub Issues:** 1-3 days
- **Pull Requests:** 2-5 days
- **Email:** 2-7 days

**We're volunteers!** Please be patient. 💙

## 🌟 Special Thanks

**Thank you to all contributors!**

Every contribution matters:
- Bug reports help us improve
- Feature ideas shape the roadmap
- Documentation helps users
- Code makes things real
- Sharing grows the community

**You're making UX research better for everyone!** 🚀

---

## 🚀 Ready to Contribute?

1. 🔍 **Find** an issue or idea
2. 💬 **Discuss** your approach
3. 🔧 **Code** your contribution
4. ✅ **Test** thoroughly
5. 📤 **Submit** your PR
6. 🎉 **Celebrate** being awesome!

**Questions?** Open an issue or discussion. We're here to help!

---

<div align="center">
    <h3>Let's build something amazing together! 💙</h3>
    <p>
        <a href="https://github.com/justogm/RemoteGazeUX/issues">Browse Issues</a> •
        <a href="https://github.com/justogm/RemoteGazeUX/discussions">Join Discussions</a> •
        <a href="../support.md">Get Support</a>
    </p>
</div>
