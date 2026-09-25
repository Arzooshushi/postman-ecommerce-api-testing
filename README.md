# Postman Ecommerce API Testing

A portfolio API testing project built in **Postman** using the **DummyJSON** ecommerce API.

## Project Overview

This project covers authentication, product APIs, cart CRUD operations, environment variables, positive and negative testing, automated assertions, and Collection Runner execution.

## Tools & Technologies

- Postman
- REST API
- JSON
- JavaScript assertions (`pm.test`, `pm.expect`)
- DummyJSON API
- GitHub

## API Scenarios Covered

1. **User Login** — POST `/auth/login`
2. **Get User Profile** — GET `/auth/me`
3. **Get All Products** — GET `/products`
4. **Get Single Product** — GET `/products/{{product_id}}`
5. **Search Products** — GET `/products/search?q=phone`
6. **Add Product to Cart** — POST `/carts/add`
7. **Get User Carts** — GET `/carts/user/1`
8. **Update Cart** — PUT `/carts/1`
9. **Delete Cart** — DELETE `/carts/1`
10. **Get Invalid Product** — GET `/products/999999`
11. **Invalid Login** — POST `/auth/login`

## Test Coverage

The collection includes automated checks for:

- HTTP status codes: `200`, `201`, `400`, `404`
- Response properties and data types
- Non-empty arrays
- Product ID validation
- Cart creation, update, and deletion
- Quantity and total calculations
- Error message validation
- Invalid credential handling
- Access token presence/absence
- Dynamic environment variables

## Environment Variables

After importing the environment, set:

| Variable | Value |
|---|---|
| `base_url` | `https://dummyjson.com` |
| `product_id` | `10` |
| `token` | Leave blank before the run |

The login request automatically stores the returned access token in the `token` environment variable.

## How to Run

1. Import the Postman collection.
2. Import the Postman environment.
3. Set `base_url` and `product_id` as shown above.
4. Select **Ecommerce Environment - GitHub**.
5. Open Collection Runner.
6. Select all requests.
7. Run 1 iteration.
8. Review the test summary.

## Final Collection Run

- **Requests:** 11
- **Automated Tests:** 52
- **Passed:** 52
- **Failed:** 0
- **Errors:** 0
- **Skipped:** 0

## Positive & Negative Testing

Positive flows cover successful login, profile retrieval, product retrieval/search, and cart CRUD operations.

Negative flows include:

- Invalid product ID → expected `404 Not Found`
- Invalid login credentials → expected `400 Bad Request`
- Verification that no access token is returned for invalid login

## Notes

DummyJSON is a mock/simulated API. Write operations such as create, update, and delete return simulated responses and do not persist changes as a real production database would.

## Repository Files

- `Ecommerce API Project.postman_collection.json`
- `Ecommerce Environment - GitHub.postman_environment.json`
- `README.md`
- `screenshots/collection-runner-result.png`

## Author

Created as a hands-on API testing portfolio project using Postman.
