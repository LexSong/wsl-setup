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

## Install Nix under WSL

[Source](https://dev.to/notriddle/installing-nix-under-wsl-2eim)

    sudo mkdir /etc/nix
    sudo vim /etc/nix/nix.conf

`/etc/nix/nix.conf`
>     # Work around missing cgroups support https://github.com/Microsoft/WSL/issues/994
>     sandbox = false
>     # Work around incorrect file locking https://github.com/Microsoft/WSL/issues/2395
>     use-sqlite-wal = false

## Install Nix

[Nix Package Manager Guide](https://nixos.org/nix/manual/)

    sh <(curl https://nixos.org/nix/install)
