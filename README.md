# Catalyst Notification API

A .NET 6.0 web service that handles notification management and delivery.

## 🎯 Overview

The Catalyst Notification API is a microservice designed to manage and process notifications. It provides a RESTful API interface for creating, sending, and managing notifications across different channels.

## 🏗️ Architecture

Diagram: 
![SVG Image](/Catalyst.Notification-arch.svg)

The solution consists of three main projects:
- **Catalyst.Notification.API**: Main API project with controllers and configuration
- **Catalyst.Notification.BusinessServices**: Core business logic and service implementations
- **Catalyst.Notification.Utility**: Shared utilities and helper functions

## 🔧 Technical Stack

- **.NET 6.0**: Core framework
- **MongoDB**: Primary database for notification storage
- **Redis**: Caching layer
- **Azure Key Vault**: Secure configuration management
- **Application Insights**: Monitoring and telemetry
- **Swagger/OpenAPI**: API documentation
- **FluentValidation**: Request validation
- **NLog**: Logging framework

## 🚀 Features

- API versioning support
- Notification creation and management
- Caching for improved performance
- Comprehensive logging and monitoring
- Input validation
- Swagger documentation
- Azure integration

## 📋 Prerequisites

- .NET 6.0 SDK
- MongoDB
- Redis
- Azure subscription (for Key Vault and App Insights)

## ⚙️ Configuration

The application uses various configuration sources:
- appsettings.json
- Azure Key Vault
- Environment variables

Key configuration sections:
json
{
"MongoDB": {
"ConnectionString": "your_connection_string",
"DatabaseName": "notifications_db"
},
"Redis": {
"ConnectionString": "your_redis_connection"
},
"Azure": {
"KeyVault": {
"Vault": "your_keyvault_name"
}
}
}

## 🏃‍♂️ Running the Application

1. Clone the repository
bash
git clone [repository-url]

2. Update configuration settings

3. Run the application
bash
dotnet run --project Catalyst.Notification.API


## 📚 API Documentation

Once running, access the Swagger documentation at:
https://localhost:5001/swagger

Key endpoints:
- `POST /api/notifications`: Create new notification
- `GET /api/notifications`: Get notifications list
- `GET /api/notifications/{id}`: Get specific notification
- [Add other main endpoints...]

## 🔒 Security

- Azure Key Vault for secrets management
- [Add other security features...]

## 🔍 Monitoring

The application uses:
- Application Insights for performance monitoring
- NLog for structured logging
- Custom metrics and traces

## 🚦 Health Checks

Health check endpoint: `/health`
Monitors:
- MongoDB connection
- Redis connection
- Overall API health

## 📦 Dependencies

Key packages:
- Asp.Versioning.Mvc
- MongoDB.Driver
- StackExchange.Redis
- FluentValidation
- [Other major dependencies...]

## 🛠️ Development

### Code Style
- Uses StyleCop for code analysis
- Follows .NET coding conventions
- EditorConfig for consistent styling

### Branch Strategy
- main: Production-ready code
- develop: Development branch
- feature/*: New features
- bugfix/*: Bug fixes

## 📄 License

[Add your license information]

## 👥 Contributing

[Add contribution guidelines]

## 🆘 Support

[Add support contact information]

---

For more information or support, please contact [your contact information]

## 🧪 Testing (TBC)

The application includes comprehensive testing using:
- SpecFlow (BDD testing)
- NUnit
- FluentAssertions
- Moq

To run tests:
bash
dotnet test