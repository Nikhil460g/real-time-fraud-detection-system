# Service Communication Matrix

| Source Service | Destination Service | Communication Type | Protocol |
|---------------|--------------------|-------------------|----------|
| API Gateway | Transaction Ingestion Service | Synchronous | REST |
| Transaction Ingestion Service | Kafka Event Bus | Asynchronous | Kafka |
| Kafka Event Bus | Fraud Rules Service | Asynchronous | Kafka |
| Kafka Event Bus | Machine Learning Service | Asynchronous | Kafka |
| Kafka Event Bus | Graph Analysis Service | Asynchronous | Kafka |
| Fraud Rules Service | Risk Assessment Service | Synchronous | REST |
| Machine Learning Service | Risk Assessment Service | Synchronous | REST |
| Graph Analysis Service | Risk Assessment Service | Synchronous | REST |
| Risk Assessment Service | Case Management Service | Synchronous | REST |
| Case Management Service | Notification Service | Asynchronous | Kafka |