# Base image
FROM ubuntu:latest

# Update and upgrade
RUN apt-get update && apt-get upgrade -y

# Install python and pip
RUN apt-get install -y python3 python3-pip

# Fix EXTERNALLY-MANAGED issue (some systems need this)
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set working directory
WORKDIR /app

# Copy the Flask app
COPY ./api.py /app/api.py

# Expose port 5252 (optional but good practice)
EXPOSE 5252

# Run Flask server
CMD ["python3", "api.py"]
