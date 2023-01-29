[![CircleCI](https://dl.circleci.com/status-badge/img/gh/kolaoba/udacity-devops-project4-operationalize_ml_api/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/kolaoba/udacity-devops-project4-operationalize_ml_api/tree/main)

## Project Overview

This project contains a Machine Learning Microservice, built on **Scikit-Learn**. It contains a model that predicts house prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle [here](https://www.kaggle.com/c/boston-housing). 

## What does this project do?

- Run a docker container
- Upload container into a public registry (hub.docker.com)
- Run the deployed application in a Kubernetes cluster
- Integrate with CircleCI for continuous integration

## Requirements
 - Python 3.7
 - Docker
 - minikube

## SET UP AND CONFIGURE LOCALLY
1. Docker
 - install docker as descibed [here](https://docs.docker.com/engine/install/ubuntu/)
2. Kubernetes
 - Run `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
 - Run `sudo install minikube-linux-amd64 /usr/local/bin/minikube`
 - Run `minikube start` to start minikube

## START PROJECT HERE 

### Step 0
- Fork and clone this repo to your local repository

### Step 1: Set up the environment
* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate

### Step 2: Install dependencies
- Install dependencies by running `make install`
- (Optionally) Lint application (requires hadolint)

### Step 3: Create Flask App in Docker container
- Run the application on docker by calling `./run_docker.sh`

### Step 4: Upload to Docker Hub
- In the `./upload_docker.sh` file, edit the dockerpath (line 8) and username (line 12) and change the docker username to a personalized one (or leave it as is, to use the public kolaobajuluwa/flaskml:v1.0.0)
- To upload to docker hub, run `./upload_docker.sh`

### Step 5: Kubernetes deployment
- To deploy to kubernetes, run `./run_kubernetes.sh`