# Python Service

## Setup and install

Ensure you have python3, pip and venv installed. Then run:

```
python3 -m venv venv
Scripts\activate.bat
pip install -r requirements.txt
```

Copy `.env.example` and rename it to `.env`. Then fill out `SQLALCHEMY_DATABASE_URL` with a connection to your postgres database.

## How to start the server

In the current folder, run:

```
uvicorn main:app --reload
```

## Further information

- [FastAPI Docs](https://fastapi.tiangolo.com)
- [Details on database connections](https://fastapi.tiangolo.com/tutorial/sql-databases/)
