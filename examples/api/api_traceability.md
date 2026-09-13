# API Traceability Matrix — demo

| Operation | Contract area | Priority | Test Conditions | Test Cases |
|---|---|---:|---|---|
| POST /orders | valid request | P0 | ATCND-001 | ATC-001 |
| POST /orders | required productId | P1 | ATCND-002 | ATC-002 |
| POST /orders | quantity minimum | P1 | ATCND-003 | ATC-003 |
| POST /orders | quantity maximum | P1 | ATCND-004 | ATC-004 |
| GET /orders | limit boundaries | P2 | ATCND-005, ATCND-006 | ATC-005, ATC-006 |
| GET /orders/{orderId} | not found | P1 | ATCND-007 | ATC-007 |
