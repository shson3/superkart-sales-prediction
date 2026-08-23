# Use a minimal base image with Python 3.11 installed.
# 3.11 rather than 3.9 because Streamlit 1.56 and requests 2.33 both need
# Python 3.10 or newer, and it keeps the two images on the same base.
FROM python:3.11-slim

# Set the working directory inside the container to /app
WORKDIR /app

# Copy all files from the current directory on the host to the container's /app directory
COPY . .

# Install Python dependencies listed in requirements.txt
RUN pip3 install -r requirements.txt

# Define the command to run the Streamlit app on port 8501 and make it accessible externally
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0", "--server.enableXsrfProtection=false"]