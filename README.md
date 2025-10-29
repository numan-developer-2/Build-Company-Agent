  # 🤖 UniAgent - Advanced AI Assistant

A next-generation, cinematic AI assistant with advanced features including **conversation memory**, **voice output (TTS)**, **session management**, and multi-modal interactions. Built with Flask backend and OpenAI API integration.

## 🆕 What's New in UniAgent v4.0

- ✅ **Conversation Memory** - Messages persist across sessions
- ✅ **Session Management** - Context-aware conversations
- ✅ **Voice Output (TTS)** - AI responses can be spoken aloud
- ✅ **Enhanced Error Handling** - Graceful error recovery
- ✅ **3D Holographic UI** - Iron Man-inspired interface
- ✅ **Message History** - Auto-restore previous conversations
- ✅ **Unique Branding** - Custom UniAgent identity

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-3.0.0-green.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## ✨ Features

### 🎯 Core Capabilities
- **💬 Text Chat** - Natural conversation with GPT-4
- **🎤 Voice Input** - Speech-to-text with Whisper API
- **🖼️ Image Analysis** - Visual understanding with GPT Vision
- **📄 Document Q&A** - Extract and analyze PDF, DOCX, CSV files

### 🎨 UI/UX Features
- **Cinematic animations** with GSAP
- **Glassmorphism design** with blur effects
- **Responsive layout** (mobile, tablet, desktop)
- **Dark/Light theme** toggle
- **Reusable modal component** for all interactions
- **Typing indicators** and smooth transitions
- **Auto-scrolling chat** interface

---

## 🏗️ Technology Stack

### Frontend
- HTML5
- CSS3 (Custom variables, animations)
- JavaScript (ES6+)
- GSAP (Animation library)
- Font Awesome (Icons)

### Backend
- Python 3.8+
- Flask (Web framework)
- OpenAI Python SDK
- Flask-CORS

### APIs
- OpenAI ChatGPT (gpt-4o-mini)
- OpenAI Whisper (voice transcription)
- OpenAI Vision (image analysis)

---

## 📁 Project Structure

```
uni-chatbot/
├── app.py                      # Flask backend
├── config.py                   # Configuration & API keys
├── requirements.txt            # Python dependencies
├── .env                        # Environment variables
├── README.md                   # Documentation
├── templates/
│   └── index.html             # Main HTML template
├── static/
│   ├── css/
│   │   ├── style.css          # Main styles
│   │   └── modal.css          # Modal component styles
│   └── js/
│       ├── script.js          # Main application logic
│       └── modal.js           # Modal component
└── uploads/                    # Temporary file storage
```

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8 or higher
- OpenAI API key
- Modern web browser

### Step 1: Clone or Download
```bash
cd uni-chatbot
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Configure API Key
Edit the `.env` file or `config.py`:
```env
OPENAI_API_KEY=your-api-key-here
SECRET_KEY=your-secret-key-here
```

### Step 5: Run the Application
```bash
python app.py
```

The application will start at: **http://localhost:5000**

---

## 🎮 Usage Guide

### 1️⃣ Text Chat
- Type your message in the input box
- Press **Enter** or click the send button
- AI responds in real-time

### 2️⃣ Voice Input
- Click the **microphone icon** 🎤
- Allow microphone access
- Speak your message
- Click "Stop Recording"
- AI transcribes and responds

### 3️⃣ Image Analysis
- Click the **image icon** 🖼️
- Select an image file
- Enter your question about the image
- Click "Analyze Image"
- AI describes the image content

### 4️⃣ Document Q&A
- Click the **paperclip icon** 📎
- Select a document (PDF, DOCX, CSV, TXT)
- Enter your question
- Click "Analyze Document"
- AI extracts text and answers

---

## 🔧 Configuration

### API Models
Edit `config.py` to change models:
```python
CHAT_MODEL = 'gpt-4o-mini'        # Text chat model
VISION_MODEL = 'gpt-4o-mini'      # Image analysis model
WHISPER_MODEL = 'whisper-1'       # Voice transcription model
```

### File Upload Limits
```python
MAX_CONTENT_LENGTH = 16 * 1024 * 1024  # 16MB
ALLOWED_EXTENSIONS = {'txt', 'pdf', 'png', 'jpg', 'jpeg', 'gif', 'doc', 'docx', 'csv', 'xlsx', 'mp3', 'wav', 'webm'}
```

### CORS Settings
```python
CORS_ORIGINS = ['*']  # Allow all origins (change for production)
```

---

## 🎨 Customization

### Theme Colors
Edit CSS variables in `static/css/style.css`:
```css
:root {
    --accent-primary: #6366f1;
    --accent-secondary: #8b5cf6;
    --bg-primary: #f5f7fa;
    /* ... more variables */
}
```

### Modal Component
The modal is fully reusable. Example usage:
```javascript
modal.open({
    title: 'Custom Modal',
    body: '<p>Your content here</p>',
    confirmText: 'OK',
    onConfirm: () => {
        // Your action
    }
});
```

---

## 📡 API Endpoints

### POST `/chat`
**Text chat endpoint**
```json
Request:
{
    "message": "Hello, how are you?"
}

Response:
{
    "status": "success",
    "reply": "I'm doing great! How can I help you?"
}
```

### POST `/voice`
**Voice transcription endpoint**
```
Form Data:
- audio: audio file (webm, mp3, wav)

Response:
{
    "status": "success",
    "transcription": "Hello world",
    "reply": "AI response here"
}
```

### POST `/image`
**Image analysis endpoint**
```
Form Data:
- image: image file
- question: "What is in this image?"

Response:
{
    "status": "success",
    "reply": "This image shows..."
}
```

### POST `/file`
**Document analysis endpoint**
```
Form Data:
- file: document file
- question: "Summarize this document"

Response:
{
    "status": "success",
    "reply": "The document discusses...",
    "extracted_text": "First 500 chars..."
}
```

---

## 🐛 Troubleshooting

### Issue: API Key Error
**Solution:** Verify your OpenAI API key in `.env` or `config.py`

### Issue: Microphone Not Working
**Solution:** 
- Check browser permissions
- Use HTTPS or localhost
- Try a different browser

### Issue: File Upload Fails
**Solution:**
- Check file size (max 16MB)
- Verify file type is supported
- Ensure `uploads/` folder exists

### Issue: CORS Error
**Solution:** Check `CORS_ORIGINS` in `config.py`

---

## 🔒 Security Notes

### Production Deployment
1. **Never commit `.env` file** to version control
2. **Use environment variables** for API keys
3. **Restrict CORS origins** to your domain
4. **Enable HTTPS** for voice recording
5. **Add rate limiting** to prevent abuse
6. **Validate all file uploads** thoroughly

### Example Production Config
```python
# config.py
import os

class Config:
    OPENAI_API_KEY = os.environ.get('OPENAI_API_KEY')
    SECRET_KEY = os.environ.get('SECRET_KEY')
    CORS_ORIGINS = ['https://yourdomain.com']
```

---

## 📊 Performance Tips

1. **Use caching** for repeated queries
2. **Implement rate limiting** on API calls
3. **Compress images** before uploading
4. **Clean up uploads folder** periodically
5. **Use CDN** for static assets in production

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License.

---

## 👨‍💻 Developer

**UniSoftware Team**

For support or questions, please open an issue on GitHub.

---

## 🙏 Acknowledgments

- OpenAI for GPT-4, Whisper, and Vision APIs
- GSAP for animation library
- Flask community for excellent documentation
- Font Awesome for icons

---

## 🔮 Future Enhancements

- [ ] Multi-language support
- [ ] Chat history persistence
- [ ] User authentication
- [ ] File export (PDF, TXT)
- [ ] Voice output (TTS)
- [ ] Code syntax highlighting
- [ ] Markdown rendering
- [ ] Image generation (DALL-E)
- [ ] Conversation memory
- [ ] Custom AI personalities

---

**Made with ❤️ by UniSoftware**
