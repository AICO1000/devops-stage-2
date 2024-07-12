<<<<<<< HEAD
FROM python:3.10-slim

=======
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
>>>>>>> bfefaed774b8b32fdc770d0b14a589f767ff9c8f
WORKDIR /app

# Install Poetry
RUN pip install poetry

<<<<<<< HEAD
# Copy pyproject.toml and poetry.lock
COPY pyproject.toml poetry.lock /app/
=======
# Install Poetry dependencies
RUN poetry install
>>>>>>> bfefaed774b8b32fdc770d0b14a589f767ff9c8f

# Install dependencies
RUN poetry install --no-root

# Copy the rest of the application
COPY . /app

<<<<<<< HEAD
# Run the prestart script
RUN chmod +x /app/prestart.sh
RUN /app/prestart.sh

CMD ["poetry", "run", "uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
=======
# Command to run the backend server
CMD ["poetry", "run", "uvicorn", "app.main:app", "--reload", "--host", "0.0.0.0", "--port", "8000"]
>>>>>>> bfefaed774b8b32fdc770d0b14a589f767ff9c8f
