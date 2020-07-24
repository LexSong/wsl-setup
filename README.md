# Setting Up a WSL Environment

## Install the Windows Subsystem for Linux

Open PowerShell as Administrator and run:

    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
    
## Install Ubuntu

* Download and install [Linux distro packages](https://docs.microsoft.com/en-us/windows/wsl/install-manual) 
* Setting up a new Linux user account

* Update and upgrade packages

        sudo apt update
        sudo apt upgrade
    
See the [WSL documentation](https://docs.microsoft.com/zh-tw/windows/wsl/about) for more details.

## Prepare installing Nix under WSL

    sudo -i
    mkdir /etc/nix
    # Work around missing cgroups support https://github.com/Microsoft/WSL/issues/994
    echo 'sandbox = false' >> /etc/nix/nix.conf
    # Work around incorrect file locking https://github.com/Microsoft/WSL/issues/2395
    echo 'use-sqlite-wal = false' >> /etc/nix/nix.conf
    exit

[Source](https://dev.to/notriddle/installing-nix-under-wsl-2eim)

## Install Nix

    curl https://nixos.org/nix/install | bash
    
[Nix Package Manager Guide](https://nixos.org/nix/manual/)

## Install Miniconda

    wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh
