## Description
Proxy server with REST API for handling fund transfer and stock transfer

## Specification
1. Endpoint for creating fund transfer
2. Endpoint for creating stock transfer

## Flow
First validate the request to another service (in this case dummyserver which is a REST API server). If the request valid then insert the request to database.

## Data model
1. Fund Transfer Database
    - accountNo varchar
    - amount int
    - status varchar (W: Request(default), X: Executed, C: Cancelled)

2. Stock Transfer Database
    - accountNo varchar
    - stock varchar
    - amount int
    - status varchar (W: Request(default), X: Executed, C: Cancelled)

3. Fund Transfer Validation Payload
    - account_no string
    - amount int

4. Stock Transfer Validation Payload
    - account_no string
    - stock string
    - amount int

## Dummy Server
- Address: http://localhost:5000
- Fund Transfer Endpoint: /fund
- Fund Transfer Limit: 1000000
- Stock Transfer Endpoint: /stock
- Stock Transfer Limit: 1000

## Tech Stack
- Database: PostgreSQL
- REST API Framework: github.com/labstack/echo/v4
- SQL Library: github.com/jmoiron/sqlx
- Database Driver: github.com/lib/pq
- HTTP Client: github.com/go-resty/resty
- Architecture: Adaptation to Hexagonal/Clean Architecture
