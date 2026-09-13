# API Test Conditions — demo

- **ATCND-001** — POST /orders принимает валидный request body — P0.
- **ATCND-002** — POST /orders отклоняет запрос без `productId` — P1.
- **ATCND-003** — POST /orders отклоняет `quantity < 1` — P1.
- **ATCND-004** — POST /orders отклоняет `quantity > 20` — P1.
- **ATCND-005** — GET /orders принимает `limit=1` — P2.
- **ATCND-006** — GET /orders принимает `limit=100` — P2.
- **ATCND-007** — GET /orders/{orderId} возвращает `404` для неизвестного ID — P1.
