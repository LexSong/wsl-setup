# Setting Up a WSL Environment

## Install WSL 2

1. Open the Command Prompt as Administrator and run: 

   ```batch
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```

   **Restart** the machine to enable WSL and Virtual Machine Platform.

2. Download and install the [WSL2 Linux kernel update package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi).
3. Set WSL 2 as the default version:

   ```batch
   wsl --set-default-version 2
   ```

## Install AlpineWSL

1. Download [AlpineWSL](https://github.com/yuk7/AlpineWSL/releases).
2. Extract the zip file.
3. Run `Alpine.exe` to extract rootfs and register to WSL.

## Install Packages and Create the Default User

Run `Alpine.exe` again to open the shell as **root**:

```shell
# Upgrade installed packages
apk -U upgrade

# Install required packages
apk add --no-cache curl sudo xz

# Create the wheel group as sudoers
echo '%wheel ALL=(ALL) ALL' > /etc/sudoers.d/wheel

# Create new user and add to the wheel group
adduser --ingroup wheel <USERNAME>

# Leave the root shell
exit
```

To change the default user, run:

```batch
Alpine.exe config --default-user <USERNAME>
```

## Install Nix

```shell
# Download and install Nix 
curl -L https://nixos.org/nix/install | sh

# Update the shell profile for Nix
echo ". /home/<USERNAME>/.nix-profile/etc/profile.d/nix.sh" >> ~/.profile
```

## Install Miniconda

```shell
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

## References

- [WSL 2 Installation Guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
- [Wsldl documentation for AlpineWSL](https://wsldl-pg.github.io/docs/)
- [A minimal Nix development environment on WSL.](https://cbailey.co.uk/posts/a_minimal_nix_development_environment_on_wsl)
- [Nix Package Manager Guide](https://nixos.org/manual/nix/stable/)
