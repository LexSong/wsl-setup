# Setting Up a WSL Environment

***This doc is currently being revised and updated to WSL 2.***

### [WSL 2 Installation Guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

1. Open PowerShell as Administrator and run:

       dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
       dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    
   to enable WSL and Virtual Machine Platform.
   
2. Download and install the Linux kernel update package:

   [WSL2 Linux kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
   
3. Set WSL 2 as the default version:

       wsl --set-default-version 2

### Install [AlpineWSL](https://github.com/yuk7/AlpineWSL)

* Download the latest release [here](https://github.com/yuk7/AlpineWSL/releases).
* Extract the zip file.
* Run `Alpine.exe` to extract rootfs and register to WSL.

## Guide to Install Nix on Alpine Linux.

[A minimal Nix development environment on WSL.](https://cbailey.co.uk/posts/a_minimal_nix_development_environment_on_wsl)

## Install Nix

    sh <(curl -L https://nixos.org/nix/install)
    
[Nix Package Manager Guide](https://nixos.org/nix/manual/)

## Install Miniconda

    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh
