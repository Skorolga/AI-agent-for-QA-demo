# API Analysis — demo

## Operations

### POST /orders — Create order

Request body:

- `productId`: string, required, minLength 1
- `quantity`: integer, required, min 1, max 20

Responses:

- `201` — order created
- `400` — invalid request

### GET /orders — List orders

Query:

- `limit`: optional integer, 1..100

Response:

- `200`

### GET /orders/{orderId} — Get order

Path parameter:

- `orderId`: required string

Responses:

- `200`
- `404`

## Contract gaps

OpenAPI не определяет:

- authentication;
- rate limits;
- idempotency for `POST /orders`;
- error response schema;
- pagination beyond `limit`.
