Pydantic is a Python library that provides an easy and convenient way to validate and manipulate data. During validation, Pydantic checks each field in the data against the type hints and validation rules defined in the data model. If the data does not meet the requirements, Pydantic raises an error and stops the validation process. If the data is valid, Pydantic *creates an instance of the data model, populates it with the incoming data, and returns it to the user*.

Pydantic also provides advanced features, such as *field aliasing*, *custom validation functions*, and support for *nested data models*, making it possible to handle a wide range of data validation scenarios. Additionally, Pydantic supports *serialization* and *deserialization*, allowing data to be converted to and from Python data structures, JSON, and other formats as needed.
```python
from pydantic import BaseModel, validator

class User(BaseModel):
    username: str
    password: str
    age: int

    @validator('password')
    def password_must_be_strong(cls, v):
        if len(v) < 8:
            raise ValueError('Password must be at least 8 characters long.')
        return v

# Validate incoming data
user_data = {'username': 'johndoe', 'password': 'password', 'age': 30}
user = User(**user_data) # the "**" unpacks the user_data into keyword arguments
```
Result:
```
Raises a ValueError: Password must be at least 8 characters long.
```

### Integrating Pydantic with FastAPI

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    username: str
    password: str
    age: int

@app.post("/user")
async def create_user(user: User):
    return {"username": user.username, "age": user.age}
```

In this example, a `User` data model is defined using Pydantic. The `User` model is then used as a parameter in the `create_user` endpoint, allowing FastAPI to automatically validate incoming data against the `User` model. If the data is not valid, FastAPI will automatically return an error to the client.





#### Reference
[vegibit.com](https://vegibit.com/what-is-pydantic-and-how-is-it-used/)