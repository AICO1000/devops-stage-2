# Use an official Python image as the base image
FROM python:3.12-slim

# Install curl and bash
RUN apt-get update && apt-get install -y curl bash

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

# Add Poetry to PATH
ENV PATH="/root/.local/bin:$PATH"

# Verify Poetry installation
RUN poetry --version

# Set the working directory
WORKDIR /app

# Copy the pyproject.toml and poetry.lock files
COPY pyproject.toml poetry.lock ./

# Install Poetry dependencies
RUN poetry install

# Copy the rest of the application files
COPY . .

# Expose port 8000
EXPOSE 8000

# Command to run the backend server
CMD ["poetry", "run", "uvicorn", "app.main:app", "--reload", "--host", "0.0.0.0", "--port", "8000"]
