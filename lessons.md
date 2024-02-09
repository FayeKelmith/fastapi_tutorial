# Notes taken FastAPI documentation

## Query Parameters

- When you declare other function parameters that are not part of the path parameters, they are automatically interpreted as "query" parameters.
- The query is the set of key-value pairs that go after the `?` in a URL, separated by `&`.
- Query parameters are optional, and have default values.
- If you declare a query parameter without a default value, it will be required. If you declare it with a default value, it will be optional.
- If you declasre query parameters in the path operation function, they will be validated and converted to the right type, if needed.

## Request Body

- A request body is data sent by the client to your API. A response body is the data your API sends to the client.
- Our API almost always needs to send a response body. But it doesn't always need to receive a request body.
- When we make a post request, containing a request body and a path parameter, FastAPI will recognize the request body and the path parameter, and will know which one is which.
- request body + path + querry parameters; FastAPI will recognize each of them and take the data from the correct place.

## Pydantic Models

- Pydantic is a library that enforces type hints at runtime, and provides user-friendly errors when data is invalid.

## Body - Multiple Parameters

- item_id: int, item: Item, user: User, importance: Annotated[int, Body()]
- The `Annotated` type is used to add metadata to the parameters. In this case, it's used to add metadata to the `importance` parameter, to specify that it should be read as a body parameter.
- Pydantic fields can be used to declare the type, validation and metadata of the parameters.
