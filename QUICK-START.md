# ⚡ Quick Start Guide

## 🎯 Get Running in 5 Minutes

**New to coding? No problem!** Follow these exact steps:

### Step 1: Install Python (if needed)

1. Go to [python.org/downloads](https://python.org/downloads)
2. Click the big yellow "Download Python" button
3. Run the installer
4. **IMPORTANT**: Check ✅ "Add Python to PATH" 
5. Click "Install Now"

### Step 2: Download Smart Doc Checker

1. **Option A - Easy Way** (if you have Git):
   ```
   git clone https://github.com/Fraze-byte/Smart-Doc-Checker.git
   ```

2. **Option B - Manual Way**:
   - Go to https://github.com/Fraze-byte/Smart-Doc-Checker
   - Click green "Code" button
   - Click "Download ZIP"
   - Extract the ZIP file

### Step 3: Open Terminal/Command Prompt

- **Windows**: Press `Win + R`, type `cmd`, press Enter
- **Mac**: Press `Cmd + Space`, type `terminal`, press Enter
- **Linux**: Press `Ctrl + Alt + T`

### Step 4: Navigate to the Project

```bash
cd Smart-Doc-Checker
```
*(Replace with the actual path if you downloaded to a different location)*

### Step 5: Setup the Environment

Copy and paste these commands **one by one**:

```bash
python -m venv venv
```

**Then activate it:**

**Windows users:**
```bash
venv\Scripts\activate
```

**Mac/Linux users:**
```bash
source venv/bin/activate
```

### Step 6: Install Required Software

```bash
pip install -r requirements.txt
```
*(This will take 1-2 minutes)*

### Step 7: Get Your FREE API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. **Copy the key** (it looks like: `AIzaSyBBJ5gMwH0AsuBN92G5i35-zoSEwVq5pWY`)

### Step 8: Launch the App

```bash
streamlit run streamlit_app.py
```

### Step 9: Use the App!

1. Your browser will automatically open to `http://localhost:8501`
2. **Enter your API key** in the sidebar (paste what you copied)
3. **Upload some documents** (PDF, Word, or text files)
4. **Click "Analyze Documents"**
5. **See the magic happen!** ✨

---

## 🆘 Something Not Working?

### "python is not recognized"
- You need to install Python (go back to Step 1)
- Make sure you checked "Add Python to PATH"

### "No such file or directory"
- Make sure you're in the right folder
- Use `dir` (Windows) or `ls` (Mac/Linux) to see files
- You should see `streamlit_app.py` in the list

### "Port 8501 is already in use"
- Try: `streamlit run streamlit_app.py --server.port 8502`
- Then go to `http://localhost:8502` instead

### App loads but analysis fails
- Double-check your API key is correct
- Make sure you have internet connection
- Try uploading a simple text file first

### Still stuck?
- Check the detailed [Installation Guide](INSTALLATION.md)
- Ask for help: [GitHub Issues](https://github.com/Fraze-byte/Smart-Doc-Checker/issues)

---

## 🎉 Success!

If you can upload a document and see conflict analysis results, **congratulations!** 

You're now ready to:
- Analyze your own documents for conflicts
- Generate professional reports
- Save time on document review
- Impress your colleagues 😎

**Next**: Check out the full [README](README.md) to learn about all the features!

---

*Total time: 5-10 minutes | Difficulty: Beginner | Requirements: Just a computer with internet*