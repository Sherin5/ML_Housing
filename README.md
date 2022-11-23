# ML_Housing
The second practice to do the ML Housing Project end to end with iNeuron

## Important Code for the project

### To create a virtual environment
```
virtualenv <Env name>
```

### Cd into the virtual env and use the bin folder to activate the batch file
```
cd <Env name>
```

```
source bin/activate
```

### To deactivate the base environment
```
conda deactivate
```

### To install all the required libraries from the requirements file. Create a requirements.txt file and then
```
pip install -r requirements.txt
```
 To check remote url
 ```
 git remote -v
 ```

 To setup CI/CD pipeline in Heroku, we need the following info:
 1. Heroku Email
 2. Heroku API Key : Available under "Account settings" on Heroku website
 3. Heroku app name : Create an app on Heroku

 Once we have the above info, we have to create a docker file
 ```
FROM python:3.7
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
EXPOSE $PORT
CMD gunicorn --workers=4 --bind 0.0.0.0:$PORT app:app
 ```

Build docker image(The name of the image should always be in small letter)
```
docker build -t <image_name>:<tag_name> .
```

To list all the docker images
```
docker images
```

Run docker image
```
docker run -p 5000:5000 -e PORT=5000 <image_ID>
```

To check all the running docker containers
```
docker ps
```

To stop docker container
```
docker stop <container_id>
```

