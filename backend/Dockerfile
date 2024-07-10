# Use an official Python image as the base image
FROM python:3.9-slim

# Install curl and bash
RUN apt-get update && apt-get install -y curl bash

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

# Set the working directory
WORKDIR /app

# Copy the pyproject.toml and poetry.lock files
COPY pyproject.toml poetry.lock ./

# Install Poetry dependencies
RUN ~/.local/bin/poetry install

# Copy the rest of the application files
COPY . .

# Expose port 8000
EXPOSE 8000

# Command to run the backend server
CMD ["~/.local/bin/poetry", "run", "uvicorn", "app.main:app", "--reload", "--host", "0.0.0.0", "--port", "8000"]
