# Use the latest version of Ubuntu
FROM ubuntu:latest

# Update the package list and install Python3 and pip3
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED to avoid errors with pip3 installs
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask and Flask-CORS using pip3
RUN pip3 install flask flask-cors

# Set the working directory to /app
WORKDIR /app

# Copy the Python script into the container
COPY api.py /app/api.py

# Expose port 5252 for Flask
EXPOSE 5252

# Run the Flask app
CMD ["python3", "api.py"]
