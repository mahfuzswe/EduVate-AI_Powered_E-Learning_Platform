# EduVate - AI-Powered E-Learning Platform

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![Django 4.2](https://img.shields.io/badge/Django-4.2-brightgreen)](https://www.djangoproject.com/)
[![PostgreSQL 15](https://img.shields.io/badge/PostgreSQL-15-blue)](https://www.postgresql.org/)
[![Code Style: Black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

![EduVate Platform Demo](docs/assets/eduvate-demo.gif)

An intelligent e-learning platform leveraging AI and gamification to deliver personalized learning experiences. Developed as a Software Engineering Capstone Project.

## 📌 Table of Contents
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [API Documentation](#-api-documentation)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)
- [Contact](#-contact)

## 🌟 Key Features

### 🧠 AI-Driven Learning
- **Adaptive Learning Paths**  
  Machine learning models (Scikit-learn) analyze student performance to recommend personalized content
- **Smart Quiz Generation**  
  NLP-powered question generation using Hugging Face transformers
- **Predictive Analytics**  
  Early identification of at-risk students using regression models

### 🎮 Gamification System
- Dynamic leaderboards with Elo rating system
- Achievement badges (Bronze, Silver, Gold tiers)
- XP points system with daily challenges
- Progress visualization using D3.js charts

### 🛠️ Core Functionality
- Multi-role access control (Student/Instructor/Admin)
- Course management system with rich text editor
- Real-time discussion forums with WebSocket integration
- Automated certificate generation (PDF/PNG)
- Comprehensive analytics dashboard

## 🚀 Technology Stack

| Component          | Technologies                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **Frontend**       | HTML5, CSS3, JavaScript ES6+, Chart.js, Webpack                             |
| **Backend**        | Python 3.10, Django 4.2, Django REST Framework, Celery                      |
| **Database**       | PostgreSQL 15 (with pgvector extension for embeddings)                      |
| **AI/ML**          | Scikit-learn 1.3, Hugging Face Transformers, spaCy 3.7                      |
| **DevOps**         | Docker 24.0, GitHub Actions, Nginx 1.25, Prometheus, Grafana                |
| **Security**       | JWT Authentication, OWASP ZAP, Let's Encrypt SSL                            |

## 📥 Installation

### Prerequisites
- Python 3.10+
- PostgreSQL 15
- Node.js 18.x
- Redis 7.x

```bash
# Clone repository
git clone https://github.com/yourusername/eduvate.git
cd eduvate

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/MacOS
# venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Install frontend dependencies
cd frontend
npm install
npm run build
cd ..

# Database setup
sudo -u postgres psql -c "CREATE DATABASE eduvate;"
sudo -u postgres psql -c "CREATE USER eduvate_user WITH PASSWORD 'strongpassword';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE eduvate TO eduvate_user;"

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Start development server
python manage.py runserver