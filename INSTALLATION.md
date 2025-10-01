# 📋 Complete Installation Guide

## Overview
This guide covers multiple ways to install and run Smart Doc Checker, from beginner-friendly to advanced setups.

## 🎯 Choose Your Installation Method

### 🟢 Method 1: Standard Installation (Recommended)

**Best for**: Most users, beginners, stable setup

```bash
# 1. Clone the repository
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker

# 2. Create virtual environment
python -m venv venv

# 3. Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Run the app
streamlit run streamlit_app.py
```

### 🟡 Method 2: Quick Development Setup

**Best for**: Developers, contributors, testing

```bash
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
python -m venv venv && venv\Scripts\activate && pip install -r requirements.txt
streamlit run streamlit_app.py
```

### 🟠 Method 3: Conda Environment

**Best for**: Data scientists, Anaconda users

```bash
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
conda create -n smart-doc-checker python=3.9
conda activate smart-doc-checker
pip install -r requirements.txt
streamlit run streamlit_app.py
```

### 🔴 Method 4: Global Installation (Not Recommended)

**Best for**: Single-use systems, containers

```bash
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
pip install -r requirements.txt
streamlit run streamlit_app.py
```

## 🛠️ Platform-Specific Instructions

### Windows Users

#### Prerequisites Check
```powershell
# Check Python version
python --version

# Check pip
pip --version

# Check Git
git --version
```

#### Full Windows Setup
```powershell
# If Python not installed:
# 1. Go to python.org/downloads
# 2. Download Python 3.9+
# 3. Run installer with "Add Python to PATH" checked

# Clone and setup
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
python -m venv venv
venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
streamlit run streamlit_app.py
```

### macOS Users

#### Using Homebrew (Recommended)
```bash
# Install dependencies
brew install python git

# Clone and setup
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
streamlit run streamlit_app.py
```

### Linux Users (Ubuntu/Debian)

```bash
# Install dependencies
sudo apt update
sudo apt install python3 python3-pip python3-venv git

# Clone and setup
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
streamlit run streamlit_app.py
```

## 🔑 API Key Setup Guide

### Step 1: Get Your FREE Gemini API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the generated key (starts with `AIza...`)

### Step 2: Configure the Key

#### Option A: Enter When Prompted (Easiest)
- Run the app: `streamlit run streamlit_app.py`
- Enter your API key in the sidebar when prompted
- Key is saved automatically for future use

#### Option B: Set in Configuration File
```python
# Edit config/settings.py
class AppSettings:
    GEMINI_API_KEY = "AIzaSy..." # Your actual key here
```

#### Option C: Environment Variable
```bash
# Windows
set GEMINI_API_KEY=AIzaSy...

# macOS/Linux
export GEMINI_API_KEY=AIzaSy...
```

## 🚨 Troubleshooting Common Issues

### Issue: "python is not recognized as internal command"

**Cause**: Python not in system PATH

**Solutions**:
1. **Reinstall Python** with "Add Python to PATH" checked
2. **Manual PATH addition**:
   - Windows: Add `C:\Python39` and `C:\Python39\Scripts` to PATH
   - Find Python location: `where python`
3. **Use full path**: `C:\Python39\python.exe -m venv venv`

### Issue: "No module named 'streamlit'"

**Cause**: Virtual environment not activated or packages not installed

**Solutions**:
```bash
# Make sure virtual environment is activated
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Reinstall packages
pip install -r requirements.txt
```

### Issue: "Address already in use [Errno 48]"

**Cause**: Port 8501 already occupied

**Solutions**:
```bash
# Use different port
streamlit run streamlit_app.py --server.port 8502

# Kill existing streamlit processes
# Windows:
taskkill /f /im python.exe
# macOS/Linux:
pkill -f streamlit
```

### Issue: "Permission denied" or "Access denied"

**Cause**: Insufficient permissions

**Solutions**:
```bash
# Windows (Run as Administrator)
# Or use --user flag
pip install --user -r requirements.txt

# macOS/Linux
sudo pip install -r requirements.txt
# Or use --user flag
pip install --user -r requirements.txt
```

### Issue: "SSL Certificate verification failed"

**Cause**: Corporate firewall or network restrictions

**Solutions**:
```bash
# Use trusted hosts
pip install --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org -r requirements.txt

# Or upgrade certificates
pip install --upgrade certifi
```

### Issue: "Google API Error 403: API key not valid"

**Cause**: Invalid or expired API key

**Solutions**:
1. **Verify API key**: Check it starts with "AIza" and is complete
2. **Regenerate key**: Go to Google AI Studio and create new key
3. **Check quotas**: Ensure you haven't exceeded free tier limits
4. **Enable service**: Make sure Gemini API is enabled for your project

## 🧪 Verify Installation

Run these commands to ensure everything is working:

```bash
# Check Python
python --version
# Expected: Python 3.9.x or higher

# Check virtual environment is active
where python
# Expected: Should point to venv folder

# Check Streamlit
streamlit --version
# Expected: streamlit, version 1.28.x or higher

# Check required packages
pip list | grep -E "(streamlit|google-generativeai|plotly)"
# Expected: All packages should be listed

# Test app launch
streamlit run streamlit_app.py
# Expected: Opens browser to http://localhost:8501
```

## 📦 Development Setup

For contributors and developers:

```bash
# Clone with development dependencies
git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
cd Smart-Doc-Checker

# Setup development environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install in development mode
pip install -e .
pip install -r requirements-dev.txt  # If exists

# Run tests
pytest tests/  # If tests exist

# Code formatting
black src/ components/
```

## 🌐 Network and Firewall

### Required Internet Access
The app needs internet access for:
- Google Gemini API calls (api.generativeai.google.com)
- Package installation (pypi.org)
- Streamlit metrics (optional)

### Firewall Configuration
If behind corporate firewall:
- Allow outbound HTTPS (443) to *.google.com
- Allow outbound HTTPS (443) to *.pypi.org
- Local port 8501 for browser access

### Proxy Configuration
If using corporate proxy:
```bash
# Set proxy environment variables
export HTTP_PROXY=http://proxy.company.com:8080
export HTTPS_PROXY=http://proxy.company.com:8080

# Or use pip proxy flags
pip install --proxy http://proxy.company.com:8080 -r requirements.txt
```

## 🎯 Success Indicators

You know the installation worked when:

1. ✅ `python --version` shows 3.9+
2. ✅ `streamlit run streamlit_app.py` launches without errors
3. ✅ Browser opens to http://localhost:8501
4. ✅ App interface loads with file upload area
5. ✅ You can enter/save API key successfully
6. ✅ Test document upload and analysis works

## 📞 Get Help

If you're still having issues:

1. **Check Issues**: [GitHub Issues](https://github.com/Fraze-byte/Smart-Doc-Checker/issues)
2. **Ask Questions**: [GitHub Discussions](https://github.com/Fraze-byte/Smart-Doc-Checker/discussions) 
3. **Read Docs**: Check README.md and this guide
4. **System Info**: Include Python version, OS, and error messages when asking for help

---

**Installation completed successfully? 🎉 [Start using Smart Doc Checker!](../README.md#features)**