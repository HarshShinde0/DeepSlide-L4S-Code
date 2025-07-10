# Use official Python 3.9 slim image
FROM python:3.9-slim

# Set working directory inside container
WORKDIR /app

# Copy requirements first (to leverage Docker cache)
COPY Streamlit-Frontend/requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy all source files and model weights into container
COPY Streamlit-Frontend/ .

# Expose default Streamlit port
EXPOSE 8501

# Run the Streamlit app
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
