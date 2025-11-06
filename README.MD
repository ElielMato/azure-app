# Azure App

![Go](https://img.shields.io/badge/Go-1.25-blue?logo=go)
![Gin](https://img.shields.io/badge/Gin-1.10.1-green?logo=go)
![Azure](https://img.shields.io/badge/Azure-Container%20Instances-blue?logo=microsoftazure)
![Docker](https://img.shields.io/badge/Docker-Multi%20Stage-blue?logo=docker)

Azure App is a REST API application developed with Go and Gin framework that provides telemetry integration with Azure Application Insights. The system is designed for cloud-native deployments with automated Azure Container Instances deployment and comprehensive monitoring capabilities.

## 🌟 Features

- **REST API**: Clean and efficient API endpoints with JSON responses.
- **Azure Application Insights**: Real-time telemetry, request tracking, and performance monitoring.
- **Automated Deployment**: One-command deployment to Azure Container Instances with Python script.
- **Docker Optimization**: Multi-stage Docker builds for minimal production images.
- **Configuration Management**: Flexible YAML-based configuration with environment variable support.
- **Request Middleware**: Automatic request tracking with detailed telemetry data.
- **Health Endpoints**: Application status and configuration endpoints for monitoring.

## 🛠️ Tech Stack

| Technology             | Purpose                  | Version |
| ---------------------- | ------------------------ | ------- |
| **Go**                 | Backend Language         | 1.25+   |
| **Gin**                | HTTP Web Framework       | 1.10.1  |
| **Azure App Insights** | Telemetry & Monitoring   | 0.4.4   |
| **Viper**              | Configuration Management | 1.21.0  |
| **Docker**             | Containerization         | Latest  |
| **Azure CLI**          | Cloud Deployment         | Latest  |

## 🚀 Getting Started

### Prerequisites

- Go 1.25+
- Docker
- Azure CLI
- Python 3.8+ (for deployment)

### Installation

```bash
# Clone the repository
git clone https://github.com/ElielMato/azure-app.git
cd azure-app

# Install dependencies
go mod download

# Copy configuration
cp config-example.yaml config.yaml

# Run the application
go run main.go
```

The application will be available at `http://localhost:8080`

### Docker Development

```bash
# Build and run with Docker
docker build -t azure-app:latest .
docker run -p 8080:8080 azure-app:latest

# Or use Docker Compose
docker-compose -f dockers/docker-compose.yml up -d
```

## ☁️ Azure Deployment

### Automated Deployment

```bash
# Install Python dependencies
pip install -r requirements.txt

# Configure environment
cp env-example .env
# Edit .env with your Azure settings

# Login to Azure
az login

# Deploy to Azure
python deploy.py
```

The deployment script automatically:

- Creates Azure Resource Group and Container Registry
- Builds and pushes Docker image
- Creates Service Principal with appropriate permissions
- Deploys to Azure Container Instances
- Configures public DNS and networking

### Manual Configuration

Update `.env` file with your Azure settings:

```bash
RESOURCE_GROUP="your-resource-group"
ACR_NAME="your-acr-name"
IMAGE_NAME="azure-app"
LOCATION="brazilsouth"
CONTAINER_NAME="azure-app-container"
```

## 📝 License

This project is open source software. Feel free to use, modify, and distribute according to your needs.

---

<div align="center">

**Built with ❤️ using Go, Azure, and modern cloud technologies**

</div>
