# API Design Specification

## 1. Transaction Fraud Check API

**Endpoint:**
POST /api/v1/fraud/check

**Request:**
{
  "transactionId": "TXN12345",
  "customerId": "CUST789",
  "amount": 15000,
  "merchantId": "MER456",
  "timestamp": "2025-09-01T10:15:30Z"
}

**Response:**
{
  "transactionId": "TXN12345",
  "fraudScore": 0.87,
  "decision": "REVIEW",
  "reason": "High-risk merchant + unusual amount"
}

---

## 2. Risk Scoring API

POST /api/v1/risk/score

Request:
{
  "customerId": "CUST789",
  "features": {
    "avgSpend": 12000,
    "transactionFrequency": 8,
    "locationMismatch": true
  }
}

Response:
{
  "riskScore": 0.92,
  "riskLevel": "HIGH"
}

---

## 3. ML Prediction API

POST /api/v1/ml/predict

Request:
{
  "features": [0.2, 0.8, 0.5, 0.9]
}

Response:
{
  "prediction": 0.81,
  "label": "FRAUD"
}