# FastAPI

> FastAPI framework, high performance, easy to learn, fast to code, ready for production

Source Code: https://github.com/tiangolo/fastapi

# What is FastAPI 

FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.6+ based on standard Python type hints.

The key features are:

* Fast: Very high performance, on par with NodeJS and Go (thanks to Starlette and Pydantic). One of the fastest Python frameworks available.
* Fast to code: Increase the speed to develop features by about 200% to 300%. 
* Fewer bugs: Reduce about 40% of human (developer) induced errors. 
* Intuitive: Great editor support. Completion everywhere. Less time debugging.
* Easy: Designed to be easy to use and learn. Less time reading docs.
* Short: Minimize code duplication. Multiple features from each parameter declaration. Fewer bugs.
* Robust: Get production-ready code. With automatic interactive documentation.
* Standards-based: Based on (and fully compatible with) the open standards for APIs: OpenAPI (previously known as Swagger) and JSON Schema.


# Requirements

* Python 3.6+

FastAPI stands on the shoulders of giants:

* Starlette for the web parts.
* Pydantic for the data parts.

# Installation

```py
pip install fastapi
```

* You will also need an ASGI server, for production such as Uvicorn or Hypercorn

# Demo Code

Create a file main.py with:

```py
from typing import Optional

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Optional[str] = None):
    return {"item_id": item_id, "q": q}
```

# Run Code

Run the server with:

```
> uvicorn main:app --reload
```

# Validate

Open your browser at `http://127.0.0.1:8000/items/5?q=somequery`

You will see the JSON response as:

```
{"item_id": 5, "q": "somequery"}
```

You already created an API that:

* Receives HTTP requests in the paths `/` and `/items/{item_id}`.
* Both paths take `GET` operations (also known as HTTP methods).
* The path `/items/{item_id}` has a path parameter `item_id` that should be an `int`.
* The path `/items/{item_id}` has an optional `str` query parameter `q`
