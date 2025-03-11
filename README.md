# FastAPI Simple API

This is a simple REST API built with [FastAPI](https://fastapi.tiangolo.com/). Examples are based on [FastAPI](https://fastapi.tiangolo.com/) and [Pydantic](https://docs.pydantic.dev/) documentation.

## Running the API
Start the FastAPI server using Uvicorn:
```sh
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```
Once running, the API is accessible at:
* Docs UI (Swagger): http://127.0.0.1:8000/docs
* Alternative API documentation (ReDoc): http://127.0.0.1:8000/redoc

### API Endpoints
| Method | Endpoint | Description |
 ------- | -------- | ----------- |
| GET | / | Returns a welcome message. |
| GET | /items/list | Retrieves the list of items. |
| GET | /items/{item_id} | Retrieves a specific item. |
| POST | /items/ | Creates a new item. |
| PUT | /items/{item_id} | Updates an existing item. |

### Example Requests
1. Get all items
```sh
curl -X 'GET' 'http://127.0.0.1:8000/items/list' -H 'accept: application/json'
```
2. Get an item by id
```sh
curl -X 'GET' 'http://127.0.0.1:8000/items/1' -H 'accept: application/json'
```
3. Create a new item
```sh
curl -X 'POST' 'http://127.0.0.1:8000/items/' \
-H 'Content-Type: application/json' \
-d '{
  "name": "item 4",
  "price": 10.5,
  "tax": 0.15
}'
```
4. Update an Existing Item
```sh
curl -X 'PUT' 'http://127.0.0.1:8000/items/1' \
-H 'Content-Type: application/json' \
-d '{
  "name": "updated item",
  "price": 12.0,
  "tax": 0.1
}'
```
