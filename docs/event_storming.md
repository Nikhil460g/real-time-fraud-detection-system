# Event Storming

## Transaction Lifecycle

### Main Flow
1. transaction_received
2. transaction_enriched
3. rule_evaluated
4. ml_scored
5. graph_analysis_completed
6. risk_score_calculated
7. risk_decision_made
8. notification_sent
9. case_created
10. case_assigned
11. case_investigated
12. case_resolved
13. audit_log_recorded

### Commands

1. SubmitTransaction
2. EnrichTransaction
3. EvaluateRules
4. RunMLScoring
5. PerformGraphAnalysis
6. CalculateRiskScore
7. MakeRiskDecision
8. SendNotification
9. CreateCase
10. AssignCase
11. InvestigateCase
12. ResolveCase
13. RecordAuditLog

### Aggregates

1. Transaction
2. CustomerProfile
3. FraudCase
4. Rule
5. RiskScore
6. Notification
7. AuditLog

### Event Storming Summary

The fraud detection system starts when a transaction is received. The transaction is enriched with customer and device information. Fraud rules are evaluated, machine learning scoring is performed, and graph analysis is executed. A risk score is calculated and a final decision is made. Depending on the result, notifications are sent, fraud cases are created and assigned to analysts, investigations are conducted, and all activities are recorded in audit logs for compliance and monitoring purposes.