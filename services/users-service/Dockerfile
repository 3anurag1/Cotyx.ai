# Use an official lightweight Python image as a base
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file first to leverage Docker's layer caching.
# This step is only re-run if requirements.txt changes.
COPY requirements.txt .

# Install the Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy your application's source code into the container
COPY ./src /app/src

# Command to run the FastAPI application using Uvicorn.
# --host 0.0.0.0 makes it accessible from outside the container.
# --reload enables live-reloading for development.
CMD ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]