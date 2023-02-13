# simple-flask-on-docker

This is a simple python-based flask application exposed using a nginx server via a gunicorn gateway. It also has a dockerized postgres database which can be used as the database for a more advanced python application.

## Prerequisites

### Git
Use the following URL and follow the guidelines according to your Operating System to install git.
https://github.com/git-guides/install-git

### Docker

Use the following URL and follow the guidelines according to your Operating System to install docker engine or docker desktop.
https://docs.docker.com/engine/install/

### Docker-compose

If you have already installed docker desktop, skip this step. If you installed docker engine use the following URL to install docker-compose.
https://docs.docker.com/compose/install/linux/#install-using-the-repository

### User Privileges

The user should have privileges to execute docker commands. If the user is root, skip the following steps.

Check the groups assigned for the user using the following command, which will return the groups of user *foo*. Replace *foo* with respective username.
```bash
groups foo
```

If the user is not in *docker* group, then execute the following command with a user that has sudo or root privileges. It will assign user *foo* to *docker* group. Replace *foo* with respective username.
```bash
sudo usermod -aG foo docker
```

## Setup

Run the following command to clone the Github repository to the local machine.
```bash
https://github.com/Sahan-Rathnayake/simple-flask-on-docker.git
```
Navigate into the root directory
```bash
cd simple-flask-on-docker/
```
Run the following command to build the docker images and start the containers.
```bash
docker-compose up -d --build
```

Run the following command to inspect the started containers.
```bash
docker ps
```

Open browser and navigate to http://127.0.0.1 and it should direct into a web page displaying **Hello World**

## Troubleshooting

If the web page cannot be viewed with error *ERR_CONNECTION_REFUSED*, run the following command to view the containers.
```bash
docker ps -a
```

If either **proxy** or **app** container is not ready or restarting, run the following command to inspect the logs.
```bash
# outputs logs of all services
docker-compose logs

# outputs logs of app
docker-compose logs app

# outputs logs of proxy
docker-compose logs proxy
```