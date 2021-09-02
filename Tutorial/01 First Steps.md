The simplest FastAPI file could look like this:

```py
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
async def root():
    return {"message": "Hello World"}
```
Copy that to a file main.py.

Run the live server:

> uvicorn main:app --reload

The command uvicorn main:app refers to:

* main: the file main.py (the Python "module").
* app: the object created inside of main.py with the line app = FastAPI().
* --reload: make the server restart after code changes. Only use for development


In the output, there's a line with something like:

> Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)

That line shows the URL where your app is being served, in your local machine.

## Check it

Open your browser at http://127.0.0.1:8000.

You will see the JSON response as:


{"message": "Hello World"}
