# Docker Vault
[![Docker](https://img.shields.io/badge/Docker-v.23.0.3-blue?logo=docker)](https://www.docker.com/)
[![Vault](https://img.shields.io/badge/Vault-v.1.17.1-yellow?logo=vault)](https://developer.hashicorp.com/vault/docs?product_intent=vault)

This repository contains the configuration and setup for running HashiCorp Vault in a Docker container using Docker Compose. Vault is used to securely store and access secrets, such as API keys, passwords, and certificates.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Files and Directories](#files-and-directories)
- [Building the Docker Image](#building-the-docker-image)
- [Running the Vault Container](#running-the-vault-container)
- [Using Docker Compose](#using-docker-compose)
- [Accessing the Vault UI](#accessing-the-vault-ui)

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Docker
- Docker Compose

## Files and Directories

- `Dockerfile`: The Dockerfile used to build the Vault image.
- `vault-config.hcl`: The configuration file for Vault.
- `docker-compose.yml`: Docker Compose file to set up Vault and GitLab Runner services.

## Building the Docker Image

To build the Docker image for Vault, run the following command from the root directory of this repository:

```sh
docker build -t isemenov/vault-filesystem:0.1 ./docker/vault
```

## Running the Vault Container

To run the Vault container, use the following command:

```sh
docker run -d -p 8200:8200 isemenov/vault-filesystem:0.1
```

This command runs the Vault container in detached mode and maps port 8200 of the container to port 8200 on the host machine.

## Using Docker Compose

Docker Compose is used to manage multi-container Docker applications. The provided docker-compose.yml file sets up Vault and GitLab Runner services.

To start the services, run:

```sh
docker-compose up -d
```

This command starts the containers in detached mode.

## Accessing the Vault UI

Once the containers are up and running, you can access the Vault UI by navigating to http://127.0.0.1:8200 in your web browser.
