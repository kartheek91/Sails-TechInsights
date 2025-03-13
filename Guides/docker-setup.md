# Installing Docker Desktop on Windows

## Prerequisites

- Windows 10 or Windows 11 (with Hyper-V and WSL 2 enabled)
- At least 4GB of RAM
- Administrator privileges

## Installation Steps

### Download Docker Desktop

Visit [Docker's official website](https://www.docker.com/) and download the latest version of Docker Desktop for Windows.
Workshop Screenshots\Docker Desktop Installation Window.png

### Run the Installer

1. Locate the downloaded `Docker Desktop Installer.exe` file and double-click to run it.
2. Follow the on-screen instructions to proceed with the installation.

### Complete the Installation

- Once the installation is complete, restart your system if prompted.
- Open Docker Desktop and complete the initial setup wizard.
- Verify installation by running the following command in Command Prompt (CMD) or PowerShell:
  
  ```sh
  docker --version
  ```

### If you are still confused
- Follow this page for Better Understanding: [text](https://www.geeksforgeeks.org/how-to-install-docker-on-windows/)


## Installing Docker on a Different Drive(If You Have Less Space In C Drive)

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