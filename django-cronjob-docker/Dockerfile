# Use an official Python runtime as a parent image
FROM python:3.8

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
#RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --upgrade pip && pip install -r requirements.txt
RUN pip install flower

# Make port 8000 available to the world outside this container
EXPOSE 8000

#RUN pip install gunicorn


# Define environment variable
ENV NAME World

# Run Gunicorn with the specified config file and application
CMD ["gunicorn", "-c", "gunicorn.config.py", "myproject.wsgi:application", "--bind", "0.0.0.0:8000"]

