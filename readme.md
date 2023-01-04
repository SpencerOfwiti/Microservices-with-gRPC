# Microservices with gRPC

## Setup

Create and activate a virtual environment

```shell
python -m venv venv
source venv/bin/activate
```

Install requirements

```shell
pip install -r marketplace/requirements.txt -r recommendations/requirements.txt
```

## Building and running docker images

Build docker images

```shell
docker-compose build
```

Run docker images

```shell
docker-compose up
```

## Testing

Run integration tests

```shell
docker-compose exec marketplace pytest marketplace_integration_test.py
```

## Upload images to DockerHub

Login to DockerHub

```shell
docker login
```

Upload images to DockerHub

```shell
docker push <username>/microservices-grpc-marketplace
docker push <username>/microservices-grpc-recommendations
```

## Deploying to Kubernetes

Install [Minikube](https://minikube.sigs.k8s.io/docs/start/) for a local Kubernetes cluster

Deploy microservices

```shell
kubectl apply -f kubernetes.yaml
```
