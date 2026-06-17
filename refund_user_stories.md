# Refund Feature User Stories

## 1. Submit Refund Request
**User Story:** As a user, I want to submit a refund request by providing the transaction ID, amount, currency, and optionally a reason, so that I can get refunded for a specific transaction.

**Acceptance Criteria:**
- The refund request must include transactionId, amount, and currency fields.
- The reason field is optional.
- The request is sent to the POST /refunds endpoint.
- The system processes the refund request if all required fields are valid.

## 2. Validate Refund Request Fields
**User Story:** As a system, I want to validate the refund request to ensure that all required fields (transaction ID, amount, currency) are present, so that the refund can be processed correctly.

**Acceptance Criteria:**
- The system checks for the presence of transactionId, amount, and currency in the request body.
- If any required field is missing, the system responds with a 400 Bad Request status.
- An error message indicates the missing field(s).

## 3. Handle Missing Transaction ID
**User Story:** As a system, I want to return an error response with status 400 Bad Request if the transaction ID is missing in the refund request, so that users are informed about the missing required field.

**Acceptance Criteria:**
- When the transactionId is not provided, the system returns HTTP status 400.
- The error response includes a message specifying that transactionId is required.

## 4. Handle Invalid Transaction ID
**User Story:** As a system, I want to return an error response with status 404 Not Found if the provided transaction ID is invalid or does not exist, so that users are informed about invalid refund requests.

**Acceptance Criteria:**
- The system verifies if the transactionId exists in the database.
- If the transactionId is invalid or not found, the system returns HTTP status 404.
- The error response includes a message indicating the transaction was not found.

## 5. Handle Refund Amount Exceeding Transaction Total
**User Story:** As a system, I want to return an error response with status 400 Bad Request if the refund amount exceeds the total amount of the original transaction, so that refunds are restricted to valid amounts.

**Acceptance Criteria:**
- The system compares the refund amount with the original transaction amount.
- If the refund amount is greater, the system returns HTTP status 400.
- The error response includes a message stating the refund amount exceeds the transaction total.

## 6. Handle Unsupported Currency
**User Story:** As a system, I want to return an error response with status 422 Unprocessable Entity if the currency provided in the refund request is unsupported, so that users are informed about invalid currency inputs.

**Acceptance Criteria:**
- The system checks if the currency is among supported currencies.
- If the currency is unsupported, the system returns HTTP status 422.
- The error response includes a message specifying invalid currency.

## 7. Successful Refund Response
**User Story:** As a user, I want to receive a success response with a refund ID when my refund request is processed successfully, so that I have confirmation and reference for the refund.

**Acceptance Criteria:**
- For valid refund requests, the system returns HTTP status 200.
- The response body includes status "success", a confirmation message, and the refundId.
- The refundId is unique and can be used to track the refund.
