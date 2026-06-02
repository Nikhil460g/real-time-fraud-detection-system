# Service SLA Specification

## Introduction

Service Level Agreements (SLAs) define the performance, availability, reliability, and throughput expectations for each microservice in the Real-Time Fraud Detection Platform.

## SLA Table

┌─────────────────────────────┬──────────────┬──────────────┬──────────────┬──────────────────┐
│ SERVICE NAME                │ P50 LATENCY  │ P95 LATENCY  │ AVAILABILITY │ THROUGHPUT (TPS) │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Transaction Ingestion Svc   │ < 20 ms      │ < 50 ms      │ 99.99%       │ 5000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Rule Engine Service         │ < 10 ms      │ < 30 ms      │ 99.95%       │ 5000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Machine Learning Service    │ < 30 ms      │ < 80 ms      │ 99.95%       │ 3000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Graph Analysis Service      │ < 50 ms      │ < 150 ms     │ 99.90%       │ 1000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Risk Scoring Service        │ < 20 ms      │ < 50 ms      │ 99.99%       │ 5000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Case Management Service     │ < 100 ms     │ < 250 ms     │ 99.90%       │ 500              │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Notification Service        │ < 100 ms     │ < 300 ms     │ 99.90%       │ 2000             │
├─────────────────────────────┼──────────────┼──────────────┼──────────────┼──────────────────┤
│ Audit Service               │ < 50 ms      │ < 100 ms     │ 99.99%       │ 5000             │
└─────────────────────────────┴──────────────┴──────────────┴──────────────┴──────────────────┘

## Conclusion

The SLA specification ensures that all services maintain high performance, high availability, and reliable fraud detection operations.
