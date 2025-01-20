# PetStore API Postman Collection

This repository contains a Postman collection for testing the PetStore API. The collection includes requests for creating, retrieving, updating, and deleting pets, as well as checking the inventory status.

## Collection Overview

The collection contains the following requests:

### 1. **Store**
- **InventoryTest**: Validates the response from the `/store/inventory` endpoint. The test checks:
  - Status code is 200
  - Response time is below 500ms
  - Response is in JSON format
  - All keys in the response contain numerical values

### 2. **Pet**
- **CreateNewPet**: Creates a new pet in the system. The request body includes:
  - Pet ID
  - Pet category (randomized)
  - Pet name (randomized first name)
  - Pet status (`available`)
- **PetById**: Retrieves a pet by ID.
- **FindByStatus**: Retrieves pets by their status (e.g., `available`).
- **UpdatePet**: Updates the details of an existing pet. The request body includes:
  - Pet ID
  - New name (randomized)
  - Photo URLs
  - Pet status (`pending`)
- **DeletePetById**: Deletes a pet by ID.

## Pre-Request Scripts

- **Pet ID Generation**: Ensures that the pet ID is incremented for each request to avoid conflicts.
- **Expected Name**: Sets a random pet name (`{{$randomFirstName}}`) for use in validation during tests.

## Test Scripts

Each request in the collection includes tests to validate the response, such as:
- **Status code checks**: Verifies that the response status code is 200 for successful requests.
- **Response validation**: Ensures the response time is within acceptable limits and contains the expected content type (`application/json`).
- **Pet data validation**: Ensures that the pet data is correct, including pet ID, name, photo URLs, and status.
- **Message confirmation**: For the `DELETE` request, checks that the response message confirms successful deletion.

## Variables

The collection uses the following variables:

- `baseUrl`: The base URL for the PetStore API (e.g., `https://petstore.swagger.io/`)
- `pet_id`: The ID of the pet to be used in requests (generated dynamically).
- `expected_name`: The name expected for the pet after updates.
