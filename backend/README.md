# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI and a PostgreSQL database.

## Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

## Setup Instructions

1. **Navigate to the backend directory**:
    ```sh
    cd backend
    ```

2. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```

3. **Create a Dockerfile in the backend directory**

   ```sh
    FROM python:3.8-slim
    WORKDIR /app
    COPY requirements.txt ./
    RUN pip install --no-cache-dir -r requirements.txt
    COPY . .
    EXPOSE 8000
    CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
   ```


4. **Build and Run the Backend Container**
   ```sh
   docker build -t backend .
   docker run -p 8000:8000 backend
   ```

<img width="959" alt="docker c1" src="https://github.com/Iyewumi-Adesupo/Dockerized-Full-Stack-Web-Application-Deployment/assets/135404420/9f766f1c-e7d5-4f3a-81aa-1efd05c083ad">

<img width="959" alt="docker c2" src="https://github.com/Iyewumi-Adesupo/Dockerized-Full-Stack-Web-Application-Deployment/assets/135404420/1da81442-6865-47e5-88a6-13f8480abcac">

<img width="959" alt="docker c3" src="https://github.com/Iyewumi-Adesupo/Dockerized-Full-Stack-Web-Application-Deployment/assets/135404420/5ff72e12-5aa5-4a58-a3e5-58d64278816b">

<img width="959" alt="docker c4" src="https://github.com/Iyewumi-Adesupo/Dockerized-Full-Stack-Web-Application-Deployment/assets/135404420/cac8b19d-6866-4b05-90e5-a3d55dd61e77">

<img width="953" alt="docker c5" src="https://github.com/Iyewumi-Adesupo/Dockerized-Full-Stack-Web-Application-Deployment/assets/135404420/9291a744-6f6b-4232-8f18-777da24b6b75">


5. **Set up the database with the necessary tables**:
    ```sh
    poetry run bash ./prestart.sh
    ```

5. **Run the backend server**:
    ```sh
    poetry run uvicorn app.main:app --reload
    ```

5. **Update configuration**:
   Ensure you update the necessary configurations in the `.env` file, particularly the database configuration.
