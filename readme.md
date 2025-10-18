# 🔍 Optical Character Recognition (OCR) Flask App

<div align="center">

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-1.1.1+-green.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5.0+-red.svg)
![Tesseract](https://img.shields.io/badge/Tesseract-OCR-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**Transform images into text with AI-powered OCR technology**

<img width="1911" height="921" alt="image" src="https://github.com/user-attachments/assets/a1fa4e9a-8f55-41bb-a4d7-c2fa2c109985" />

</div>

---

## 🌟 Features

- **📸 Image Upload**: Drag & drop or browse to upload images
- **🔤 Text Extraction**: Advanced OCR using Tesseract engine
- **🎨 Modern UI**: Beautiful Materialize CSS interface
- **⚡ Real-time Processing**: Instant text extraction from images
- **📱 Responsive Design**: Works on desktop, tablet, and mobile
- **🔄 Image Preprocessing**: Automatic grayscale conversion for better accuracy
- **📝 Clean Output**: Removes unwanted symbols and formats text
- **💾 File Management**: Automatic file handling and cleanup

## 🎯 Use Cases

- **📄 Document Digitization**: Convert scanned documents to editable text
- **📱 Mobile Text Extraction**: Extract text from photos taken with smartphones
- **📊 Data Entry**: Automate manual data entry from images
- **🔍 Content Analysis**: Analyze text content in images
- **📚 Educational**: Learning tool for OCR technology
- **🏢 Business**: Process invoices, receipts, and forms

## 🛠️ Technology Stack

| Component | Technology | Version |
|-----------|------------|---------|
| **Backend** | Flask | 1.1.1+ |
| **OCR Engine** | Tesseract | 3.02+ |
| **Image Processing** | OpenCV | 4.5.0+ |
| **Image Handling** | Pillow | 8.0.0+ |
| **Frontend** | Materialize CSS | Latest |
| **Language** | Python | 3.7+ |

## 🚀 Quick Start

### Prerequisites

- Python 3.7 or higher
- Tesseract OCR engine
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/BHOOMI764/Text_extraction_app.git
   cd Text_extraction_app
   ```

2. **Install Tesseract OCR**
   
   **Windows:**
   - Download from [Tesseract Windows Installer](https://github.com/UB-Mannheim/tesseract/wiki)
   - Default path: `C:\Program Files\Tesseract-OCR\tesseract.exe`
   
   **macOS:**
   ```bash
   brew install tesseract
   ```
   
   **Linux (Ubuntu/Debian):**
   ```bash
   sudo apt-get install tesseract-ocr
   ```

3. **Create virtual environment**
   ```bash
   python -m venv ocr_env
   ```

4. **Activate virtual environment**
   
   **Windows:**
   ```bash
   ocr_env\Scripts\activate
   ```
   
   **macOS/Linux:**
   ```bash
   source ocr_env/bin/activate
   ```

5. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

6. **Run the application**
   ```bash
python app.py
   ```

7. **Open your browser**
   Navigate to `http://localhost:5000`

## 📁 Project Structure

```
Text_extraction_app/
├── 📁 app/
│   ├── 📁 static/
│   │   ├── 📁 css/          # Materialize CSS files
│   │   ├── 📁 js/           # JavaScript files
│   │   ├── 📁 images/       # Static images
│   │   └── 📁 uploads/      # Uploaded images
│   ├── 📁 templates/
│   │   └── 📄 index.html    # Main template
│   ├── 📄 __init__.py      # Flask app initialization
│   └── 📄 views.py         # Main application logic
├── 📁 sample_data/
│   └── 📄 img.png          # Sample test image
├── 📄 app.py               # Application entry point
├── 📄 config.py            # Configuration settings
├── 📄 requirements.txt     # Python dependencies
├── 📄 Procfile             # Heroku deployment config
└── 📄 README.md           # This file
```

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
FLASK_ENV=development
FLASK_DEBUG=True
UPLOAD_FOLDER=app/static/uploads
MAX_CONTENT_LENGTH=16777216  # 16MB
```

### Tesseract Configuration

The app uses optimized Tesseract settings for better accuracy:

```python
custom_config = r'-l eng --oem 3 --psm 6'
```

- `-l eng`: English language
- `--oem 3`: Default OCR Engine Mode
- `--psm 6`: Uniform block of text

## 📖 API Documentation

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Home page with upload form |
| `POST` | `/` | Process uploaded image and extract text |

### Request Format

**POST /**
- **Content-Type**: `multipart/form-data`
- **Body**: `image_upload` (file)

### Response Format

```json
{
  "status": "success",
  "extracted_text": ["Line 1", "Line 2", "..."],
  "image_url": "/static/uploads/filename.png"
}
```

## 🧪 Testing

### Sample Images

Use the provided sample images in the `sample_data/` folder:

```bash
# Test with sample image
curl -X POST -F "image_upload=@sample_data/img.png" http://localhost:5000/
```

### Supported Image Formats

- **PNG** (.png)
- **JPEG** (.jpg, .jpeg)
- **BMP** (.bmp)
- **TIFF** (.tiff)
- **GIF** (.gif)

s
## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines

- Follow PEP 8 style guidelines
- Add tests for new features
- Update documentation
- Ensure backward compatibility

## 🐛 Troubleshooting

### Common Issues

**Issue**: `Tesseract not found`
```bash
# Solution: Add Tesseract to PATH or specify path
export PATH=$PATH:/usr/local/bin/tesseract
```

**Issue**: `Permission denied on uploads folder`
```bash
# Solution: Set proper permissions
chmod 755 app/static/uploads
```

**Issue**: `Module not found errors`
```bash
# Solution: Reinstall dependencies
pip install -r requirements.txt --force-reinstall
```

## 📊 Performance Tips

- **Image Size**: Smaller images process faster
- **Format**: PNG and JPEG work best
- **Quality**: Higher resolution images give better results
- **Preprocessing**: The app automatically converts to grayscale

## 🔒 Security Considerations

- File upload validation
- Image format restrictions
- Temporary file cleanup
- Input sanitization

## 📈 Future Enhancements

- [ ] Multi-language support
- [ ] Batch processing
- [ ] API rate limiting
- [ ] User authentication
- [ ] Text translation
- [ ] PDF processing
- [ ] Cloud storage integration

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Bhoomi Jaiswal**
- GitHub: [@BHOOMI764](https://github.com/BHOOMI764)
- Project Link: [https://github.com/BHOOMI764/Text_extraction_app](https://github.com/BHOOMI764/Text_extraction_app)

## 🙏 Acknowledgments

- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) for the OCR engine
- [Flask](https://flask.palletsprojects.com/) for the web framework
- [Materialize CSS](https://materializecss.com/) for the UI framework
- [OpenCV](https://opencv.org/) for image processing

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

Made with ❤️ by [Bhoomi Jaiswal](https://github.com/BHOOMI764)

</div>
