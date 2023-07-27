# Postman-API-Test

This repository contains API tests using Postman with Swagger documentation for the "MyPetStore" API.

## Test Cases

### Get pet by status "Available"
- Method: GET
- URL: [https://petstore.swagger.io/v2/pet/findByStatus?status=available](https://petstore.swagger.io/v2/pet/findByStatus?status=available)

### Get pet by status "Pending"
- Method: GET
- URL: [https://petstore.swagger.io/v2/pet/findByStatus?status=pending](https://petstore.swagger.io/v2/pet/findByStatus?status=pending)
- Tests:
  - Verify status code is 200
  - Verify "pending" is included in the response
  - Verify response time is less than 200ms

### Get pet by status "Sold"
- Method: GET
- URL: [https://petstore.swagger.io/v2/pet/findByStatus?status=sold](https://petstore.swagger.io/v2/pet/findByStatus?status=sold)
- Tests:
  - Verify status code is 200
  - Verify "sold" is included in the response
  - Verify response time is less than 200ms

### Get pet without status should return status code 405
- Method: GET
- URL: [https://petstore.swagger.io/v2/pet/](https://petstore.swagger.io/v2/pet/)
- Tests:
  - Verify status code is 405
  - Verify response time is less than 200ms

### Add new pet
- Method: POST
- URL: [https://petstore.swagger.io/v2/pet/](https://petstore.swagger.io/v2/pet/)
- Body:
  ```json
  {
    "id": 0,
    "category": {
      "id": 0,
      "name": "Catty"
    },
    "name": "Catty",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "Catty"
      }
    ],
    "status": "available"
  }
  ```
- Tests:
  - Verify status code is 200
  - Verify "Catty" is included in the response

### Get pet by ID
- Method: GET
- URL: [https://petstore.swagger.io/v2/pet/9223372036854775807](https://petstore.swagger.io/v2/pet/9223372036854775807)
- Tests:
  - Verify status code is 200

### Update existing pet ID & name
- Method: PUT
- URL: [https://petstore.swagger.io/v2/pet/](https://petstore.swagger.io/v2/pet/)
- Body:
  ```json
  {
    "id": 123,
    "category": {
      "id": 123,
      "name": "Tigress"
    },
    "name": "Tigress",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 123,
        "name": "Tigress"
      }
    ],
    "status": "available"
  }
  ```
- Tests:
  - Verify status code is 200
  - Verify "Tigress" and "123" are included in the response

### Update ID
- Method: PUT
- URL: [https://petstore.swagger.io/v2/pet/](https://petstore.swagger.io/v2/pet/)
- Body:
  ```json
  {
    "id": 8,
    "category": {
      "id": 8,
      "name": "Dx"
    },
    "name": "Dx",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 8,
        "name": "Dx"
      }
    ],
    "status": "available"
  }
  ```
- Tests:
  - Verify status code is 200
  - Verify "8" is included in the response

### Delete pet should return status code 404
- Method: DELETE
- URL: [https://petstore.swagger.io/v2/pet/8](https://petstore.swagger.io/v2/pet/8)
- Body:
  ```json
  {
    "code": 404,
    "type": "unknown",
    "message": "8"
  }
  ```
- Tests:
  - Verify status code is 404

## Collection File
- Collection file can be found in [Mypetstore.postman_collection.json](Mypetstore.postman_collection.json)

## Test Execution
1. Import the "Mypetstore.postman_collection.json" collection file into Postman.
2. Run the test cases individually or execute the entire collection.

Feel free to reach out if you have any questions or need further assistance!
