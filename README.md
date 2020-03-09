Simple example showing how to dockerize flask applications

## Pre-requisites 

To run this project, the following must be installed
- Python 3
- Docker desktop

## Steps to run flask application

`cd` into the project folder

```bash
cd python-flask-docker
```

Create a virtual environment
```bash
python3 -m venv virtual
```

Activate virtual environment
```bash 
source ./virtual/bin/activate
```

Install dependencies
```bash
pip3 install -r requirements.txt
```

Run flask project
```bash
python3 app.py
```

## Creating the Docker container

Create docker container 
```bash
docker build -t flask-app:latest .
```

## Running the container

Run docker container on port `5000` 
```bash
docker container run --publish 5000:5000 --detach --name my_flask_app flask-app
```

If everything goes right, executing the following command will list `my_flask_app`
```bash
docker container list
```

Open browser and go to http://localhost:5000 to see if the flask app is running successfully.

## Cleanup

To remove docker container
```bash
docker container rm --force my_flask_app
```

To deactivate virtual environment
```bash
deactivate
```
