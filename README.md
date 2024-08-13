# Docker-Project-Flask

This project demonstrates a simple Flask application containerized with Docker. The application returns a simple JSON message when accessed via HTTP.

## Project Structure

- **index.py**: Contains the Flask application code.
- **Dockerfile**: Instructions on how to build the Docker image for the Flask application.

## Prerequisites

- Docker installed on your machine.
- Python 3.9 or later (if running locally without Docker).

## Getting Started

#### 1. Build the Docker Image <br>

To build the Docker image, navigate to the project directory and run the following command:

```
docker build -t flask-app .
```

#### 2. Run the Docker Container <br>

After building the image, you can run the container with:

```
docker run -p 3000:3000 flask-app
```

This will start the Flask application and make it accessible at
[http://localhost:3000](http://localhost:3000)

#### 3. Access the Application <br>

Open your web browser or use a tool like _`curl`_ to access the application:

```
curl http://localhost:3000
```

#### You should see the following JSON response: <br>

```json
{
  "message": "Hey Python"
}
```

#### Dockerfile Breakdown

- _`FROM python:3-alpine3.15`_: This line sets the base image to Python 3 on Alpine Linux, a lightweight distribution.
- _`WORKDIR /app`_: This command sets the working directory inside the container to /app.
- _`COPY . /app`_: Copies all files from the current directory on the host to the /app directory in the container.
- _`RUN pip install -r requirements.txt`_: Installs the Python dependencies listed in requirements.txt.
- _`EXPOSE 3000`_: Informs Docker that the container will listen on port 3000.
- _`CMD python ./index.py`_: This command runs the Flask application when the container starts.

#### Useful Resources

- [Docker Documentation](https://docs.docker.com/)
- [Docker Hub](https://docs.docker.com/docker-hub/)