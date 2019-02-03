# Dockerizing Python Applications

### Create virtual environment
```
$ python3 -m venv env
$ source env/bin/activate
$ pip install -r requirements.txt
```

### Build Docker image
```
$ docker build -t docker-flask:latest .
```

### Run Docker container
```
$ docker run --name flaskapp -v$PWD/app:/app -p5000:5000 docker-flask:latest
```

### Stop and remove this container
```
$ docker stop flaskapp && docker rm flaskapp
```

### Run Docker container using NGINX
```
$ docker run -d --name flaskapp --restart=always -p 80:80 docker-flask:latest
```

### If we need to debug, run the container in debug mode mounting our own version of the source tree
```
$ docker run -it --name flaskapp -p 5000:5000 -v$PWD/app:/app docker-flask:latest -d
```

### Resources
* https://stackabuse.com/dockerizing-python-applications/
