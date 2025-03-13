# Installing the n8n Starter Kit

## Overview

[n8n](https://n8n.io/) is an open-source workflow automation tool that allows you to automate tasks by integrating various services and APIs. The n8n AI Starter Kit provides pre-configured AI-powered automation workflows.

## Installation Steps

### Clone the Repository

Open a terminal and run:

```sh
git clone https://github.com/n8n-io/self-hosted-ai-starter-kit.git
```

### Navigate to the Directory

```sh
cd self-hosted-ai-starter-kit
```

### Start n8n with Docker

Run the following command to start the container:

```sh
docker compose --profile cpu up
```

> **Note:** Wait until all the dependencies get installed.

### Access the n8n Interface

Once the container is running, open your browser and go to:

[http://localhost:5678](http://localhost:5678)

---

# Downloading a Model Inside Ollama (Docker)

### Navigate to the Ollama Image inside the self-hosted-ai-startup container

### Check if any model is present inside Ollama

```sh
ollama list
```

### Pull a Model

If there is no model present inside Ollama, you can pull the image of the models from the official website and search for the particular model there.

To pull a model:

```sh
ollama pull model_name
