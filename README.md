
![FastAPI Logo](fastapi.png)

--------------------------

# FastAPI Getting Started

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/LahcenEzzara/fastapi-getting-started.git
   cd fastapi-getting-started
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate # On Windows use `venv\Scripts\activate`
   ```

3. Install the required dependencies:

   ```bash
   pip install fastapi
   ```

## Running the Application

To run the FastAPI application, use the following command:

```bash
fastapi dev
```

This will start the server at http://127.0.0.1:8000.

## API Endpoints

### Root Endpoint

- URL: /
- Method: GET
- Description: Returns a greeting message.
- Response:

  ```json
  {
    "Hello": "World"
  }
  ```

### Read Item

- URL: /items/{item_id}
- Method: GET
- Description: Retrieves an item by its ID. Optionally, a query parameter q can be included.
- Parameters:
  - item_id (int): The ID of the item.
  - q (str, optional): A query string.
- Response:

  ```json
  {
    "item_id": 1,
    "q": "your_query"
  }
  ```

### Update Item

- URL: /items/{item_id}
- Method: PUT
- Description: Updates an item's information.
- Parameters:
  - item_id (int): The ID of the item.
  - item (Item): The item data to update.
- Request Body:

  ```json
  {
    "name": "Item Name",
    "price": 10.0,
    "is_offer": true
  }
  ```

- Response:

  ```json
  {
    "item_name": "Item Name",
    "item_id": 1
  }
  ```

## Data Models

### Item

The Item model is defined as follows:

```python
from pydantic import BaseModel
from typing import Union

class Item(BaseModel):
    name: str
    price: float
    is_offer: Union[bool, None] = None
```

## Copyrights

This project is licensed under the MIT License. See the LICENSE file for more details.

**© 2024 Lahcen Ezzara**
