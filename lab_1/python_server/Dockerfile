# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the Python server script and requirements file into the container
COPY server.py . 
COPY requirements.txt .

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Install requirements from lab2 file
RUN pip install -r requirements.txt

# Expose the port that your Python server will run on
EXPOSE 8000

# Run the Python server
CMD ["python", "./server.py"]
