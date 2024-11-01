# Catalyst Policy Consumer

## Overview
The Catalyst Policy Consumer is a .NET 6.0 web application designed to process and handle policy-related messages and events from multiple message brokers. It serves as a robust, scalable service that can consume messages from both Apache Kafka and Azure Service Bus, process them according to business rules, and maintain a reliable event-driven architecture.

##Diagram:
![SVG Image](/Catalyst.Consumer-arch.svg)

## Features
- 🔄 Multi-broker message consumption (Kafka and Azure Service Bus)
- 🔐 Secure configuration management with Azure Key Vault
- 📊 Real-time monitoring with Application Insights
- 📝 Comprehensive logging with NLog
- 🔍 API documentation with Swagger/OpenAPI
- 💉 Dependency Injection with Autofac
- ⚡ High-performance message processing
- 🔄 Automatic retry policies
- 🚀 Scalable architecture

## Prerequisites
- .NET 6.0 SDK
- Azure Subscription (for Key Vault and Service Bus)
- Apache Kafka cluster (if using Kafka)
- Docker (optional, for containerization)

## Configuration
The application uses various configuration sources:
- `appsettings.json`
- Azure Key Vault (for secrets)
- Environment Variables

### Required Configuration Keys

json
{
"ServiceBus": {
"ConnectionString": "<from-key-vault>",
"QueueName": "policy-queue"
},
"Kafka": {
"BootstrapServers": "localhost:9092",
"GroupId": "policy-consumer-group",
"Topics": ["policy-topic"]
},
"ApplicationInsights": {
"ConnectionString": "<from-key-vault>"
}
}

## Installation

1. Clone the repository
```bash
git clone https://github.com/your-org/Catalyst-Policy-Consumer.git
```

2. Install dependencies
```bash
dotnet restore
```

3. Configure your settings in `appsettings.json`

4. Run the application
```bash
dotnet run
```

## Docker Support
Build and run the application using Docker:

```bash
docker build -t catalyst-policy-consumer .
docker run -p 8080:80 catalyst-policy-consumer
```

## Architecture
The service follows a clean architecture pattern with the following components:

- **API Layer**: REST endpoints for health checks and monitoring
- **Consumer Layer**: Message consumption and processing logic
- **Business Logic Layer**: Core business rules and policy processing
- **Infrastructure Layer**: External service integrations

## Message Processing
The service can process messages from:
1. **Azure Service Bus**
   - Queue-based messaging
   - Dead-letter queue support
   - Message sessions (if configured)

2. **Apache Kafka**
   - Topic-based messaging
   - Consumer group management
   - Partition assignment

## Monitoring and Logging
- Application Insights integration for:
  - Request tracking
  - Dependency monitoring
  - Performance metrics
  - Exception tracking

- NLog configuration for:
  - Structured logging
  - Multiple log targets
  - Log level management

## API Documentation
Swagger UI is available at `/swagger` when running in development mode.

## Health Checks
Health endpoints are available at:
- `/health` - Overall service health
- `/health/ready` - Readiness probe
- `/health/live` - Liveness probe

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License
[Your License Here]

## Support
For support, please contact [Your Support Contact]

## Authors
- [Your Team/Organization]

## Acknowledgments
- List any third-party libraries or tools used
- Credit any inspirations or references
```

This README provides a comprehensive overview of the service, its features, and how to use it. You may want to customize it further based on your specific implementation details, requirements, and organizational standards.

The README is structured to be both informative for new developers and useful as a quick reference for experienced team members. It includes all the essential sections that a good README should have: overview, setup instructions, configuration details, architecture information, and contribution guidelines.

