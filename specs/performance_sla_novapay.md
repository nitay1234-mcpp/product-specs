# Performance SLA for Load Tests at NovaPay

## Overview
This document outlines the expected performance metrics for load testing of NovaPay services, specifically focusing on the Payment API. The SLA is based on the information obtained from the qa-automation and product-specs repositories.

## Key Performance Metrics

### Payment API
- **Response Time:** 95% of payment processing requests should complete within 2 seconds under normal load.
- **Throughput:** The system should support processing at least 1000 payment requests per minute without degradation.
- **Error Rate:** Less than 1% of payment requests should result in errors or failures.
- **Timeout Handling:** The Payment API must properly handle network timeouts, responding with HTTP status code 408 for request timeouts.

### Webhook Performance
- Webhook events should be processed and acknowledged within 1 second 95% of the time.

## Load Test Requirements
- Load tests should simulate realistic user behavior including a mix of payment methods as indicated in the qa-automation tests.
- Edge cases and error scenarios should be included to validate system robustness.

## Monitoring and Reporting
- Continuous monitoring of response times, throughput, error rates, and timeout occurrences.
- Load test reports should be generated after each major release or significant change.

## Acknowledgments
- This SLA document is informed by the existing test cases and API specifications in the NovaPay repositories.

---

For detailed API specifications and test cases, refer to the [product-specs repo](https://github.com/nitay1234-mcpp/product-specs) and [qa-automation repo](https://github.com/nitay1234-mcpp/qa-automation).