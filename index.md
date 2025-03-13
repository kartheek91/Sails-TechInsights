# Installing Docker Desktop on Windows

## Prerequisites

- Windows 10 or Windows 11 (with Hyper-V and WSL 2 enabled)
- At least 4GB of RAM
- Administrator privileges

## Installation Steps

### Download Docker Desktop

Visit [Docker's official website](https://www.docker.com/) and download the latest version of Docker Desktop for Windows.
![alt text](<Docker Desktop Installation Window.png>)
### Run the Installer

1. Locate the downloaded `Docker Desktop Installer.exe` file and double-click to run it.
2. Follow the on-screen instructions to proceed with the installation.
3. Ensure that WSL 2 and Hyper-V options are enabled during the setup.

### Complete the Installation

- Once the installation is complete, restart your system if prompted.
- Open Docker Desktop and complete the initial setup wizard.
- Verify installation by running the following command in Command Prompt (CMD) or PowerShell:
  
  ```sh
  docker --version
  ```

## Installing Docker on a Different Drive

If you wish to install Docker Desktop on a drive other than `C:\`, use the following command:

```sh
start /w "" "Docker Desktop Installer.exe" install -accept-license --installation-dir="D:\Docker\Docker" --wsl-default-data-root="D:\Docker\wsl" --windows-containers-default-data-root="D:\Docker"
```

Run this command from the directory where the `Docker Desktop Installer.exe` is located.

## Enabling Hyper-V and WSL 2 (If Not Already Enabled or If You Run Into Error After Installing Docker Desktop)

### Enable Hyper-V

Open PowerShell as Administrator and run:

```sh
dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All /NoRestart
```

Restart your computer for the changes to take effect.

### Enable Windows Subsystem for Linux (WSL) 2

Open PowerShell as Administrator and run:

```sh
dism.exe /Online /Enable-Feature /FeatureName:Microsoft-Windows-Subsystem-Linux /All /NoRestart
```

Enable the Virtual Machine Platform:

```sh
dism.exe /Online /Enable-Feature /FeatureName:VirtualMachinePlatform /All /NoRestart
```

Restart your computer.

Install the [WSL 2 Kernel Update Package](https://aka.ms/wsl2kernel) from Microsoft’s official site.

Set WSL 2 as the default version:

```sh
wsl --set-default-version 2
```

Once these features are enabled, you can proceed with Docker Desktop installation.

---

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
