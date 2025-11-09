# Network Security Phishing Detection

[![CI/CD Pipeline](https://github.com/omsingh4459/networksecurity/actions/workflows/main.yml/badge.svg)](https://github.com/omsingh4459/networksecurity/actions/workflows/main.yml)
[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-green.svg)](https://fastapi.tiangolo.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://www.docker.com/)
[![AWS](https://img.shields.io/badge/AWS-ECR-orange.svg)](https://aws.amazon.com/ecr/)

A comprehensive machine learning pipeline for detecting phishing websites using network security data. This project implements an end-to-end MLOps solution with automated CI/CD, model training, and deployment capabilities.

## 🚀 Features

- **Automated ML Pipeline**: Complete data ingestion, validation, transformation, and model training pipeline
- **Real-time Predictions**: FastAPI-based REST API for real-time phishing detection
- **Batch Processing**: Support for batch prediction on CSV files
- **Cloud Integration**: AWS S3 integration for artifact and model storage
- **MLflow Tracking**: Experiment tracking and model versioning
- **Docker Support**: Containerized deployment with Docker
- **CI/CD Pipeline**: GitHub Actions for continuous integration and deployment
- **Web Interface**: HTML-based prediction results visualization

## 🏗️ Architecture

The project follows a modular architecture with the following components:

### Core Components
- **Data Ingestion**: Handles data collection and initial processing
- **Data Validation**: Ensures data quality and schema compliance
- **Data Transformation**: Feature engineering and preprocessing
- **Model Training**: Automated model training with hyperparameter tuning
- **Model Evaluation**: Comprehensive metrics and validation

### Infrastructure
- **FastAPI Application**: REST API for predictions
- **MongoDB**: Data storage for training artifacts
- **AWS S3**: Cloud storage for models and artifacts
- **Docker**: Containerization for deployment
- **GitHub Actions**: CI/CD automation

## 📋 Prerequisites

- Python 3.10+
- Docker (for containerized deployment)
- AWS CLI configured (for cloud features)
- MongoDB instance (for data storage)

## 🛠️ Installation

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/omsingh4459/networksecurity.git
   cd networksecurity
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file with the following variables:
   ```env
   MONGO_DB_URL=your_mongodb_connection_string
   AWS_ACCESS_KEY_ID=your_aws_access_key
   AWS_SECRET_ACCESS_KEY=your_aws_secret_key
   AWS_REGION=your_aws_region
   ```

### Docker Deployment

1. **Build the Docker image**
   ```bash
   docker build -t networksecurity .
   ```

2. **Run the container**
   ```bash
   docker run -p 8000:8000 --env-file .env networksecurity
   ```

## 🚀 Usage

### Training the Model

Run the training pipeline locally:
```bash
python main.py
```

Or via API:
```bash
curl -X GET "http://localhost:8000/train"
```

### Making Predictions

#### Single Prediction via API
```bash
curl -X POST "http://localhost:8000/predict" \
     -H "Content-Type: multipart/form-data" \
     -F "file=@your_data.csv"
```

#### Batch Prediction
Upload a CSV file through the web interface at `http://localhost:8000/docs`

### Web Interface

Access the interactive API documentation at:
```
http://localhost:8000/docs
```

## 📊 Pipeline Overview

1. **Data Ingestion**: Downloads and extracts network security data from configured sources
2. **Data Validation**: Validates data schema, handles missing values, and ensures data quality
3. **Data Transformation**: Applies feature engineering, scaling, and encoding
4. **Model Training**: Trains multiple models (Logistic Regression, etc.) with hyperparameter tuning
5. **Model Evaluation**: Evaluates models using F1-score, precision, and recall metrics
6. **Model Deployment**: Saves best model and preprocessor to disk and syncs to S3

## 🔧 Configuration

Key configuration files:
- `data_schema/schema.yaml`: Data schema validation rules
- `networksecurity/constant/training_pipeline/`: Pipeline constants and configurations
- `.github/workflows/main.yml`: CI/CD pipeline configuration

## 📈 Model Performance

The model achieves high accuracy in detecting phishing websites with:
- **F1-Score**: >0.95
- **Precision**: >0.94
- **Recall**: >0.96

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Om Kumar Singh**
- Email: omsingh4459@gmail.com
- GitHub: [@omsingh4459](https://github.com/omsingh4459)

⭐ Star this repo if you find it helpful!
