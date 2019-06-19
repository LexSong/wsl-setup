# Setting Up a WSL Environment

## Install the Windows Subsystem for Linux

Open PowerShell as Administrator and run:

    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
    
## Install Ubuntu

* Install [Ubuntu](https://www.microsoft.com/store/productId/9NBLGGH4MSV6) from Microsoft Store.

* Setting up a new Linux user account

* Update and upgrade packages

        sudo apt update
        sudo apt upgrade
    
See the [WSL documentation](https://docs.microsoft.com/zh-tw/windows/wsl/about) for more details.

## Prepare installing Nix under WSL

[Source](https://dev.to/notriddle/installing-nix-under-wsl-2eim)

    sudo -i 
    mkdir /etc/nix
    # Work around missing cgroups support https://github.com/Microsoft/WSL/issues/994
    echo 'sandbox = false' >> /etc/nix/nix.conf
    # Work around incorrect file locking https://github.com/Microsoft/WSL/issues/2395
    echo 'use-sqlite-wal = false' >> /etc/nix/nix.conf
    exit

## Install Nix

    curl https://nixos.org/nix/install | bash
    
[Nix Package Manager Guide](https://nixos.org/nix/manual/)
