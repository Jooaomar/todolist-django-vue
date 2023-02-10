# Use an official Python runtime as the base image
FROM python:3.7-slim-buster

# Set the working directory to /app
WORKDIR /Api

# Copy the current directory contents into the container at /app
COPY . /Api

# Install the required packages
RUN pip install -r requirements.txt

EXPOSE 8000

# Set the default command to run the Django development server
CMD ["bash", "exec.sh"]