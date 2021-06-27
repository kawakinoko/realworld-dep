> ### Example docker-compose yaml for dockerized [Node backend](https://github.com/kawakinoko/node-express-realworld-example-app) and [Angular frontend](https://github.com/kawakinoko/angular-realworld-example-app) that adheres to the [RealWorld](https://github.com/gothinkster/realworld-example-apps) API spec.

# Prerequisite
You need to install docker-compose

Please refer [instruction](https://docs.docker.com/compose/install/)

# Getting started
To get the orchestrated service using docker-compose yaml

- Clone this repo
- Build backend/frontend docker image. Please refer [Node backend](https://github.com/kawakinoko/node-express-realworld-example-app) and [Angular frontend](https://github.com/kawakinoko/angular-realworld-example-app) section `Dockerize the project`.

### Run Dockerized image
#### Dev Environment
1. Using docker command
```bash
$  docker run -p <Port to expose>:3000 realworld-backend:dev
```
2. Using docker-compose 
   
Please refer https://github.com/kawakinoko/realworld-dep
```bash
$  git clone https://github.com/kawakinoko/realworld-dep.git
$  cd realworld-dep
$  docker-compose up mongo realworld-be
```
#### Prod Environment
1. Using docker command

You need to input `mongodb_uri` and `secret`
```bash
$  docker run -p <Port to expose>:3000 -e NODE_ENV=production -e MONGODB_URI=<mongodb_uri> -e SECRET=<secret> realworld-backend
```
2. Using docker-compose

Please refer https://github.com/kawakinoko/realworld-dep

You can change `MONGODB_URI` and `SECRET` using docker-compose.prod.yaml
```bash
$  git clone https://github.com/kawakinoko/realworld-dep.git
$  cd realworld-dep
$  docker-compose -f docker-compose.yaml -f docker-compose.prod.yaml up mongo realworld-be
```
