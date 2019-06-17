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
