# 🎯 Time Verify AI

**Dashboard**
<img width="1901" height="945" alt="image" src="https://github.com/user-attachments/assets/685bc996-4c4b-45a8-b331-e65d4246569a" />

**Initial doc with image/screenshots**
<img width="1913" height="1009" alt="image" src="https://github.com/user-attachments/assets/824a91c8-852b-42c5-925c-669c772fef1c" />


**Processing**
<img width="1051" height="870" alt="image" src="https://github.com/user-attachments/assets/d9667292-5904-4785-891f-ba228e5562c3" />

**completed processing**
<img width="991" height="869" alt="image" src="https://github.com/user-attachments/assets/3670936f-28cb-4156-9355-b2cac770fb66" />

**Excel**
<img width="1694" height="859" alt="image" src="https://github.com/user-attachments/assets/b2d87e16-ecba-4bba-800c-864d80fb1b1b" />



**Intelligent Timesheet Processing Solution Powered by AI**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)](https://flask.palletsprojects.com)
[![Claude AI](https://img.shields.io/badge/Claude%20AI-3.5%20Sonnet-orange.svg)](https://anthropic.com)
[![Red Hat](https://img.shields.io/badge/Red%20Hat-OpenShift-red.svg)](https://openshift.com)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Time Verify AI revolutionizes timesheet processing by automatically extracting data from DOCX files using advanced AI technology. Transform manual timesheet verification from a 10+ minute manual process to 30 seconds of automated accuracy.

## ✨ Features

- **🤖 AI-Powered Extraction**: Leverages Claude 3.5 Sonnet for intelligent document analysis
- **📄 Bulk Processing**: Process multiple DOCX files simultaneously with real-time progress tracking
- **🎯 High Accuracy**: 95% accuracy rate with intelligent status detection
- **⚡ Lightning Fast**: Reduces processing time from 10+ minutes to 30 seconds per timesheet
- **📊 Real-time Dashboard**: Live metrics showing documents processed, hours extracted, and time savings
- **🔍 Smart Status Detection**: Automatically recognizes submission status from visual cues (yellow highlighting)
- **📈 Excel Export**: Formatted output with color-coded status indicators
- **🚀 Enterprise Ready**: Deployed on Red Hat OpenShift with containerized architecture
- **🔒 Secure Processing**: Enterprise-grade security with temporary file management

## 🏗️ Architecture

```
┌─────────────┐    ┌─────────────────┐    ┌─────────────────┐    ┌─────────────┐
│  DOCX Files │───▶│  Flask Web App  │───▶│   Claude AI     │───▶│   Results   │
│  (Upload)   │    │  (Processing)   │    │  (Analysis)     │    │  (Excel)    │
└─────────────┘    └─────────────────┘    └─────────────────┘    └─────────────┘
                           │                        │
                           ▼                        ▼
                   ┌─────────────────┐    ┌─────────────────┐
                   │  Image          │    │  Data           │
                   │  Extraction     │    │  Validation     │
                   └─────────────────┘    └─────────────────┘
```

## 🛠️ Tech Stack

- **Backend**: Python Flask with multithreaded processing
- **AI Engine**: Anthropic Claude 3.5 Sonnet for computer vision analysis
- **Document Processing**: Python-docx, PIL for image extraction and optimization
- **Data Export**: OpenPyXL for formatted Excel generation
- **Deployment**: Red Hat OpenShift with Podman container runtime
- **Frontend**: HTML5, CSS3, JavaScript with real-time updates

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- Claude API key from Anthropic
- Red Hat OpenShift (for production deployment)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/your-username/time-verify-ai.git
cd time-verify-ai
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Set environment variables**
```bash
export CLAUDE_API_KEY=your_claude_api_key_here
export PORT=8080
export HOST=0.0.0.0
```

4. **Run the application**
```bash
python app.py
```

5. **Access the application**
```
http://localhost:8080
```

### Docker Deployment

```bash
# Build the container
docker build -t time-verify-ai .

# Run with environment variables
docker run -p 8080:8080 \
  -e CLAUDE_API_KEY=your_api_key \
  time-verify-ai
```

### Red Hat OpenShift Deployment

```bash
# Deploy to OpenShift
oc new-app python:3.8~https://github.com/your-username/time-verify-ai.git
oc expose svc/time-verify-ai
```

## 📋 Usage

### 1. Upload Timesheet Files
- Navigate to the web interface
- Upload single or multiple DOCX files containing timesheet screenshots
- Supported formats: .docx, .doc

### 2. Process Documents
- Click "Process Files" to start AI analysis
- Monitor real-time progress and processing status
- View live dashboard metrics

### 3. Download Results
- Export processed data as formatted Excel file
- Includes color-coded status indicators
- Contains employee names, dates, hours, and submission status

### 4. API Endpoints

```bash
# Upload files for processing
POST /process-bulk

# Check processing status
GET /status/{job_id}

# Download results
GET /download/{job_id}

# Get dashboard metrics
GET /dashboard

# Health check
GET /health
```

## 📊 Performance Metrics

| Metric | Before (Manual) | After (AI-Powered) | Improvement |
|--------|----------------|-------------------|-------------|
| **Processing Time** | 10+ minutes | 30 seconds | **95% faster** |
| **Accuracy Rate** | ~85% (human error) | 95% | **+10% accuracy** |
| **Cost per Timesheet** | $5-8 (labor) | $0.50 | **90% cost reduction** |
| **Weekly Time Savings** | N/A | 16+ hours | **Significant ROI** |

## 🔧 Configuration

### Environment Variables

```bash
# Required
CLAUDE_API_KEY=your_anthropic_api_key

# Optional
PORT=8080                    # Application port
HOST=0.0.0.0                # Application host
MAX_CONTENT_LENGTH=104857600 # Max upload size (100MB)
```

### Red Hat Environment Detection

The application automatically detects and optimizes for Red Hat environments:
- OpenShift deployment
- RHEL compatibility
- Podman container runtime
- systemd integration

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Code formatting
black app.py
flake8 app.py
```

## 📝 API Documentation

### Process Files
```http
POST /process-bulk
Content-Type: multipart/form-data

{
  "docx_files": [file1.docx, file2.docx, ...]
}
```

### Response Format
```json
{
  "job_id": "uuid-string",
  "total_files": 2,
  "message": "Processing started"
}
```

### Status Check
```http
GET /status/{job_id}
```

```json
{
  "status": "completed",
  "processed": 2,
  "total": 2,
  "total_entries": 45
}
```

## 🔒 Security

- **Data Privacy**: Temporary file processing with automatic cleanup
- **API Security**: Environment-based API key management
- **Container Security**: Red Hat enterprise security standards
- **No Persistent Storage**: Sensitive timesheet data never stored permanently

## 📈 Roadmap

- [ ] **Multi-language Support**: Support for multiple document languages
- [ ] **Advanced Analytics**: Enhanced reporting and insights dashboard
- [ ] **API Integration**: Direct integration with popular HRIS systems
- [ ] **Mobile App**: Native mobile application for timesheet capture
- [ ] **OCR Enhancement**: Support for scanned document processing
- [ ] **Audit Trail**: Comprehensive processing history and audit logs

## 🐛 Troubleshooting

### Common Issues

**Claude API Key Not Working**
```bash
# Verify your API key
export CLAUDE_API_KEY=your_key_here
echo $CLAUDE_API_KEY
```

**Memory Issues with Large Files**
```bash
# Increase container memory limits
docker run -m 2g time-verify-ai
```

**OpenShift Deployment Issues**
```bash
# Check pod logs
oc logs deployment/time-verify-ai
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team

- **[Aravind G]** - Lead Developer

## 🙏 Acknowledgments

- [Anthropic](https://anthropic.com) for Claude AI technology
- [Red Hat](https://redhat.com) for OpenShift platform
- [Flask](https://flask.palletsprojects.com) community for the web framework
- Open source contributors and the Python community

## 📞 Support

- 📧 Email: Aravind.G@IBM.com

---

**Built with ❤️ for enterprise timesheet processing automation**

*Transform your HR workflow today with Time Verify AI - where manual timesheet processing becomes a thing of the past.*
