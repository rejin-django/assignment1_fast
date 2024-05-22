# Address Book API

This is a minimal address book API built with FastAPI. It allows users to create, update, delete, and retrieve addresses. The addresses are stored in an SQLite database, and the API can also retrieve addresses within a given distance from specified coordinates.

## Features

- Create a new address with name and coordinates (latitude and longitude).
- Retrieve an address by its ID.
- Update an existing address.
- Delete an address.
- Retrieve addresses within a specified distance from given coordinates.

## Requirements

- Python 3.7+
- FastAPI
- Uvicorn
- SQLAlchemy
- Databases
- Pydantic
- Geopy

## Installation

1. Clone the repository:

   git clone https://github.com/yourusername/address-book-api.git
   cd address-book-api

Create a virtual environment and activate it:
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
Install the dependencies:

pip install -r requirements.txt
Running the Application
To run the application, execute the following command in your terminal:

uvicorn main:app --reload
The API will be available at http://127.0.0.1:8000.

API Endpoints
You can access the API documentation and interact with the endpoints using FastAPI's built-in Swagger UI at http://127.0.0.1:8000/docs.

Create a new address
Endpoint: POST /addresses/
Request Body:

{
  "name": "Home",
  "latitude": 40.712776,
  "longitude": -74.005974
}

Response:
{
  "id": 1,
  "name": "Home",
  "latitude": 40.712776,
  "longitude": -74.005974
}

Retrieve an address by ID
Endpoint: GET /addresses/{address_id}

Response:
{
  "id": 1,
  "name": "Home",
  "latitude": 40.712776,
  "longitude": -74.005974
}
Update an existing address
Endpoint: PUT /addresses/{address_id}
Request Body:

{
  "name": "Office",
  "latitude": 37.774929,
  "longitude": -122.419418
}
Response:

{
  "id": 1,
  "name": "Office",
  "latitude": 37.774929,
  "longitude": -122.419418
}
Delete an address
Endpoint: DELETE /addresses/{address_id}
Response:
{
  "detail": "Address deleted"
}
Retrieve addresses within a distance
Endpoint: GET /addresses/
Query Parameters:
lat: Latitude of the center point.
lon: Longitude of the center point.
distance: Distance in kilometers.
Response:

[
  {
    "id": 1,
    "name": "Home",
    "latitude": 40.712776,
    "longitude": -74.005974
  },
  {
    "id": 2,
    "name": "Office",
    "latitude": 37.774929,
    "longitude": -122.419418
  }
]
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
FastAPI
SQLAlchemy
Pydantic
Geopy

Contact
For any questions or suggestions, please open an issue or contact the repository owner.
