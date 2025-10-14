# Use official Python base image
FROM python:3.10-slim

# Install system dependencies
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy dependency file
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your code
COPY . .

# Environment variables
ENV HF_CLIP_MODEL="openai/clip-vit-base-patch32"
ENV PORT=8080

# Expose port
EXPOSE 8080

# Start the FastAPI app
CMD ["uvicorn", "ml_service:app", "--host", "0.0.0.0", "--port", "8080"]
