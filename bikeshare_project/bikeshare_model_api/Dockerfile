
# Use the official Python image from the Docker Hub
FROM python:3.10

# Set the working directory
WORKDIR /app

# Copy the wheel file into the container
COPY bikeshare_model_api/bikeshare_model-0.0.1-py3-none-any.whl .

# Copy application files to the container
COPY bikeshare_project/bikeshare_model_api /app

# Copy application files to the container
COPY . /app

# Upgrade PIP
RUN pip install --upgrade pip

# Install the model from the .whl file
RUN pip install bikeshare_model-0.0.1-py3-none-any.whl

# Install the dependencies
RUN pip install -r requirements.txt

# Expose the port the app runs on
EXPOSE 8000

# Start the FASTAPI application
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
