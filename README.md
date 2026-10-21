# 🎬 PyTube Gemini — AI-Powered YouTube Video Explorer

> A modern desktop YouTube player that combines **YouTube search, video insights, Google Gemini AI explanations, and multilingual translation** in a single application.

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Gemini](https://img.shields.io/badge/Google-Gemini%20AI-8AB4F8?logo=google)](https://ai.google.dev/)
[![YouTube API](https://img.shields.io/badge/YouTube-Data%20API%20v3-red?logo=youtube&logoColor=white)](https://developers.google.com/youtube/v3)
[![CustomTkinter](https://img.shields.io/badge/UI-CustomTkinter-1f6feb)](https://github.com/TomSchimansky/CustomTkinter)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](#license)

---

## ✨ Overview

**PyTube Gemini** is a Python-based desktop application designed to make YouTube discovery and video understanding easier.

Search for videos, explore their metadata, and ask **Google Gemini** to generate an AI-powered explanation based on the video's available information. The application also supports multiple languages, including **English, Hindi, Hinglish, Japanese, French, German, Spanish, Bengali, Urdu, Tamil, and Telugu**.

The project combines:

- 🔎 **YouTube Data API v3** for video and channel information
- 🤖 **Google Gemini** for AI-powered video explanations
- 🌐 **Google Cloud Translation API** for multilingual output
- 🖥️ **CustomTkinter** for a modern desktop interface
- 🖼️ **Pillow** for thumbnail/image processing
- ⚡ **Threaded API requests** to keep the UI responsive

---

## 🚀 Features

### 🔎 YouTube Search

Search YouTube directly from the desktop application and browse relevant videos without needing to open a separate browser.

### 🤖 Gemini AI Explainer

Select a video and generate an AI-powered explanation using Google Gemini.

The AI analysis includes:

- **Video Summary**
- **Main Topics Covered**
- **Target Audience**
- **Worth Watching?**
- **Quick Stats Analysis**

The application uses information such as:

- Video title
- Channel
- Description
- Duration
- Views
- Likes
- Tags

to construct the AI prompt.

### 🌍 Multilingual AI Explanations

Choose from multiple supported languages:

| Language | Support |
|---|---|
| 🇮🇳 Hinglish | ✅ |
| 🇮🇳 Hindi | ✅ |
| 🇬🇧 English | ✅ |
| 🇯🇵 Japanese | ✅ |
| 🇫🇷 French | ✅ |
| 🇩🇪 German | ✅ |
| 🇪🇸 Spanish | ✅ |
| 🇧🇩 Bengali | ✅ |
| 🇵🇰 Urdu | ✅ |
| 🇮🇳 Tamil | ✅ |
| 🇮🇳 Telugu | ✅ |

Hinglish receives a dedicated prompt designed to produce a natural combination of Hindi and English.

### 🎨 Modern Dark UI

The application uses **CustomTkinter** to provide a modern dark interface with:

- YouTube-inspired styling
- Video cards
- Thumbnail previews
- Gemini AI panel
- Language selector
- Responsive controls
- Status indicators

### 📊 Video Metadata

The application can retrieve useful YouTube metadata including:

- Title
- Channel
- Description
- Duration
- Views
- Likes
- Tags
- Thumbnail

### ⚡ Responsive Interface

Network operations are handled using background threads so API requests don't unnecessarily freeze the desktop interface.

---

## 🏗️ Architecture

The application follows a simple desktop-client architecture:

```text
┌───────────────────────────────┐
│        CustomTkinter UI       │
│                               │
│  Search → Video Results       │
│              │                │
│              ▼                │
│       Video Information       │
└───────────────┬───────────────┘
                │
                ▼
       ┌─────────────────┐
       │ YouTube Data API│
       └────────┬────────┘
                │
                ▼
       ┌─────────────────┐
       │  Gemini AI API  │
       └────────┬────────┘
                │
                ▼
       ┌─────────────────┐
       │ Google Translate│
       └────────┬────────┘
                │
                ▼
       ┌─────────────────┐
       │ AI Explanation  │
       └─────────────────┘
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python** | Application logic |
| **CustomTkinter** | Desktop GUI |
| **YouTube Data API v3** | YouTube search & metadata |
| **Google Gemini API** | AI video explanations |
| **Google Cloud Translation API** | Translation |
| **Requests** | HTTP/API communication |
| **Pillow** | Image and thumbnail processing |
| **Tkinter** | Base desktop UI functionality |

---

## 📁 Project Structure

```text
pytube-gemini/
│
├── miku.py          # Main application
├── README.md        # Project documentation
└── ...
```

---

## ⚙️ Requirements

Before running the project, make sure you have:

- Python **3.9 or newer**
- A Google Cloud project
- A Google API key
- Internet connection

The application uses the following Python packages:

```text
customtkinter
Pillow
requests
```

---

## 🔑 Google API Setup

PyTube Gemini uses Google services for YouTube data, AI generation, and translation.

### 1. Create a Google Cloud Project

Open the Google Cloud Console:

https://console.cloud.google.com/

Create a new project or select an existing project.

### 2. Enable the Required APIs

Enable the following APIs:

1. **YouTube Data API v3**
2. **Generative Language API**
3. **Cloud Translation API**

### 3. Create an API Key

Go to:

**Google Cloud Console → APIs & Services → Credentials**

Create an API key.

> **Security recommendation:** Restrict your API key to the APIs and applications where it is required. Never commit a real API key to GitHub.

---

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/prachikaneriya23/pytube-gemini.git
cd pytube-gemini
```

Create a virtual environment:

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

Install the dependencies:

```bash
pip install customtkinter Pillow requests
```

---

## 🔐 Configure Your API Key

The application can accept a Google API key through its configuration.

In `miku.py`, locate:

```python
GOOGLE_API_KEY = ""
```

and provide your key:

```python
GOOGLE_API_KEY = "YOUR_GOOGLE_API_KEY"
```

### ⚠️ Important

Do **not** commit your real API key.

For public repositories, it is strongly recommended to move secrets into environment variables or another secure configuration mechanism.

---

## ▶️ Run the Application

Start the application with:

```bash
python miku.py
```

Once launched:

1. Enter your API key if required.
2. Search for a YouTube video.
3. Browse the search results.
4. Select a video.
5. Click **Explain**.
6. Choose your preferred language.
7. Let Gemini generate the explanation.

---

## 🧠 How the AI Explanation Works

When you request an explanation, the application collects available video metadata and sends structured information to Gemini.

The prompt contains information such as:

```text
Title
Channel
Description
Duration
Views
Likes
Tags
```

Gemini then generates an explanation containing:

```text
1. Video Summary
2. Main Topics Covered
3. Who Should Watch
4. Worth Watching?
5. Quick Stats Analysis
```

For supported languages other than English and Hinglish, the generated response can additionally be passed through the Google Cloud Translation API.

---

## 🔒 Security

API keys are sensitive credentials.

**Never:**

- Commit API keys to GitHub
- Publish API keys in screenshots
- Share API keys in issues or pull requests
- Hard-code production credentials into public repositories

If a key is accidentally exposed, revoke it immediately from Google Cloud Console and generate a new one.

For production usage, consider environment variables:

```bash
GOOGLE_API_KEY=your_api_key_here
```

---

## 🧪 Example Workflow

```text
Launch Application
       │
       ▼
Search YouTube
       │
       ▼
Select Video
       │
       ▼
View Metadata
       │
       ▼
Click "Explain"
       │
       ▼
Select Language
       │
       ▼
Google Gemini
       │
       ▼
AI Explanation
       │
       ▼
Optional Translation
```

---

## 🎯 Use Cases

PyTube Gemini can be useful for:

- 📚 Understanding educational videos
- 🧑‍💻 Exploring programming tutorials
- 🎓 Quickly reviewing lecture content
- 🌍 Understanding content in another language
- 🔍 Discovering useful YouTube content
- 🤖 Experimenting with Gemini-powered applications
- 🖥️ Learning desktop GUI development with Python
