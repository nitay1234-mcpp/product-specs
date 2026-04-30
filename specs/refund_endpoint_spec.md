# Refund Endpoint Specifications

## Endpoint: POST /refunds

### Overview
This endpoint allows for processing refund requests for transactions.

### Request Body Schema:
```json
{
  "transactionId": "string",    // Required: ID of the transaction being refunded
  "amount": "number",           // Required: Amount to refund
  "currency": "string",         // Required: Currency of the refund (e.g., "USD")
  "reason": "string"            // Optional: Reason for the refund
}
```

### Test Cases:

- **Successful Refund**:
  - Description: Verify that a valid refund request is processed successfully.
  - Expected Response:
  ```json
  {
    "status": "success",
    "message": "Refund processed successfully.",
    "refundId": "refund123"
  }
  ```

- **Error Handling**:
  - Missing Required Fields: Return a 400 Bad Request for missing `transactionId`.
  - Invalid Transaction ID: Return a 404 Not Found for invalid IDs.
  - Amount Exceeds Transaction Total: Return a 400 Bad Request if the refund amount exceeds the original transaction amount.
  - Invalid Currency: Return a 422 Unprocessable Entity for unsupported currencies.
