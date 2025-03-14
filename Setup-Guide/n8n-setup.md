# Installing the n8n Starter Kit

## Pre-requisite

- Install Git by searching `git download for windows`
  
  ![Git Screenshot](https://github.com/user-attachments/assets/6526acc4-14e7-4d12-855b-d3208df2de70)

- Install the 64 bit version.

## Overview

[n8n](https://n8n.io/) is an open-source workflow automation tool that allows you to automate tasks by integrating various services and APIs. The n8n AI Starter Kit provides pre-configured AI-powered automation workflows.

## Installation Steps

### Clone the Repository

- Open a terminal and run:

```sh
git clone https://github.com/n8n-io/self-hosted-ai-starter-kit.git
```

![Git Clone N8N Screenshot](https://github.com/user-attachments/assets/00f57987-406e-434c-998d-a268820f5528)

- Create a new directory in your system and then clone the repository there

![git clone repo screenshot](https://github.com/user-attachments/assets/e497e7f3-046f-40c5-8fb1-d5dfd438d5e3)


### Navigate to the Directory

```sh
cd self-hosted-ai-starter-kit
```

### Start n8n with Docker

- Run the following command to start the container:

```sh
docker-compose --profile cpu up
```

![docker compose up command for n8n ](https://github.com/user-attachments/assets/f53610a1-968d-4dcf-b231-f207b15d86a9)


> **Note:** Wait until all the dependencies get installed.

### Access the n8n Interface

Once the container is running, open your browser and go to: [http://localhost:5678](http://localhost:5678)

---

![n8n Startup Page](https://github.com/user-attachments/assets/fc654e2d-a117-4b73-8e87-799f19a33b0a)

Fill-In All The Fields And Then Click Next. Then You'll be redirected to the dashboard or the Home-Page Of N8N

![n8n home screen](https://github.com/user-attachments/assets/8ac3c840-4940-442d-ac96-e57c52f5d677)


# Downloading a Model Inside Ollama (Docker)

### Navigate to the Ollama Image inside the self-hosted-ai-startup container

![Docker Show Up fro n8n](https://github.com/user-attachments/assets/f3190c8e-d5bd-46c9-8f7a-d62e18b3a7ef)


### Check if any model is present inside Ollama

```sh
ollama list
```

![Ollama image](https://github.com/user-attachments/assets/ad91b961-8829-4217-973b-2dea2e2ee7f9)


### Run Particular Model Inside Ollama

If you wish to install a particular model from Ollama navigate to their official page and search for the model

![ollama pull llama](https://github.com/user-attachments/assets/13d36f23-7d85-47e7-9d68-984c5449961b)


Once you find a suitable model you can run it using 
```sh
ollama run model_name
```

![Ollama pull docxker](https://github.com/user-attachments/assets/3e95cf11-90ab-4025-a5ae-5fa320512995)


