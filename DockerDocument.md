# Docker Running configuration

## Docker Installation
sudo apt-get update
sudo apt-get install -y docker.io
sudo service docker status
sudo docker images
sudo docker info
sudo docker version

## Test Images
sudo docker run hello-world
sudo docker images

## Build Docker Image
sudo docker build -t [container-name]:[tag] .
sudo docker build -t flask-sample-one:latest .

## Run the Docker Container
sudo docker run -d -p [current-port]:[port-to-set] [container-name]
sudo docker run -d -p 5000:5000 flask-sample-one

## Reference
### A. Docker Setup
[Basic Docker Flask App](http://containertutorials.com/docker-compose/flask-simple-app.html)
[Advance Docker Flask App](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xix-deployment-on-docker-containers)
[Advance Docker Flask App](http://containertutorials.com/py/docker-py.html)
[Nginx ALphine OS Docker](https://github.com/jazzdd86/alpine-flask)

### B. Example Docker Learning curve
[Docker Compose Flask APP](https://github.com/stavshamir/docker-tutorial)
[Docker Compose Flask APP](https://runnable.com/docker/python/docker-compose-with-flask-apps)
[Docker Compose Flask App Nginx Mysql](https://github.com/rajdeepd/orchestrating-docker)


### C. Cloud Docker container 
[Google Cloud Compute Engine Container](https://cloudplatform.googleblog.com/2017/11/introducing-an-easy-way-to-deploy-containers-on-Google-Compute-Engine-virtual-machines.html)

### D. ML Docker Container
[Keras Inception Google Compute Docker](https://blog.murraycole.com/2017/01/22/keras-inception-v3-on-google-compute-engine/)
[Docker Data Science](https://towardsdatascience.com/whats-after-setting-up-a-gcp-computing-instance-running-a-custom-docker-container-with-tensorflow-eb0f077983c6)

## Error
1. pymysql 
[Error]-
setup.py return 1 
[Solution]- add Dockerfile before pymysql 
RUN apk add --update python3 py3-pip build-base musl python3-dev libffi libffi-dev openssl-dev
RUN pip install --upgrade pip cryptography httpie-edgegrid
