---
sidebar_position: 2
---

# Installing WarpDL

This documentation provides step-by-step instructions for installing the Warp Download Manager on your system using various package managers. By following these simple steps, you'll be able to harness the power of Warp and enjoy faster and more efficient file downloads.

## Installing WarpDL with Package Managers

Follow the instructions below to install Warp using your preferred package manager:

### Brew (macOS)

To install Warp using Brew, follow these steps:

1. Open a terminal window.
2. Run the following command:
```bash
brew install warpdl/tap/warpdl
```
3. Once the installation is complete, Warp will be ready to use.


### Snap Package Manager

To install Warp using Snap, follow these steps:

1. Open a terminal window.
2. Run the following command to install Warp:
```bash
sudo snap install warpdl
```
3. Enter your password if prompted, and confirm the installation.
4. Once the installation is complete, Warp will be ready to use.


### Scoop Package Manager (Windows)

To install Warp using Scoop, follow these steps:

1. Open a command prompt or PowerShell window.
2. If you haven't installed Scoop, run the following command to install it:
```bash
iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
```
3. Add official scoop bucket for warp:
```bash
scoop bucket add warpdl https://github.com/warpdl/scoop-bucket.git
```
4. Install Warp by executing the following command:
```bash
scoop install warpdl
```
5. Once the installation is complete, Warp will be ready to use.

### APT Package Manager (Debian/Ubuntu)

To install Warp using APT, follow these steps:

1. Open a terminal window.
2. Update the package lists by running the following command:
```bash
sudo apt-get update
```
3. Install the required packages:
```bash
sudo apt-get install ca-certificates curl gnupg -y
```
4. Add GPG key for warpdl to your APT installation:
```bash
curl -fsSL https://repo.warpdl.org/apt/gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/warpdl.gpg
``` 
5. Add repo of warpdl to your APT installation:
```bash
echo "deb [signed-by=/etc/apt/keyrings/warpdl.gpg] https://repo.warpdl.org/apt/ /" | sudo tee /etc/apt/sources.list.d/warpdl.list
```
6. Install Warp by executing the following command:
```bash
sudo apt-get install warp
```
7. Once the installation is complete, Warp will be ready to use.

### Yum (RedHat/CentOS)

To install Warp using Yum, follow these steps:

1. Import GPG Key for warpdl:
```bash
sudo rpm --import 'https://repo.warpdl.org/rpm/gpg.key'
```
2. Add yum config:
```bash 
curl -sLf --retry 3 --tlsv1.2 --proto "=https" 'https://raw.githubusercontent.com/warpdl/warp-releases/main/configs/rpm/config.rpm.txt' | sudo tee /etc/yum.repos.d/warpdl.repo
```
3. Install latest warp package:
```bash 
sudo yum update && sudo yum install warp
```
4. Once the installation is complete, Warp will be ready to use.

## Installing WarpDL using other ways
If your preferred package manager is not listed above, you can also use any of the following methods to install WarpDL:

### Git Bash

To install Warp using Git Bash, follow these steps:

1. Make bin by running the following command in your terminal:
```bash
mkdir -p $HOME/bin
```
2. Make a cURL request to install warp using shell script: 
```bash
curl -Ls --tlsv1.2 --proto "=https" --retry 3 https://cli.warpdl.org/install.sh | sh -s -- --install-path $HOME/bin
```
3. Once the installation is complete, Warp will be ready to use.

### Shell Script
You can bypass package managers and quickly install the latest version of the CLI via shell script. The script automatically downloads and installs the CLI binary most appropriate for your system's architecture. It is also fully POSIX compliant to support all linux and bsd variants with minimal dependencies.

Note that this installation method is most recommended for ephemeral environments like CI jobs. Longer-lived environments that would like to receive updates via package manager should install the CLI via that package manager.

```bash
(curl -Ls --tlsv1.2 --proto "=https" --retry 3 https://cli.warpdl.org/install.sh || wget -t 3 -qO- https://cli.warpdl.org/install.sh) | sh
```

### Docker Image
We currently publish a `ghcr.io/warpdl/warp-cli` Docker image based on `alpine`.


## Downloading Binaries

You can download all binaries and release artifacts from the [Releases](https://github.com/warpdl/warp-releases/releases/latest) page. Binaries are built for `macOS`, `Linux`, `Windows`, `FreeBSD`, `OpenBSD`, and `NetBSD`, and for `32-bit`, `64-bit`, `armv6/armv7`, and `armv6/armv7 64-bit` architectures.

You can also directly download the generated `.deb`, `.rpm`, and `.apk` packages. If a binary does not yet exist for the OS/architecture you use, please open a [GitHub Issue](https://github.com/warpdl/warp-releases).

## Verifying Installation

To ensure that Warp is successfully installed, open a command-line interface (CLI) and run the following command:

```bash
warpdl --version
```

If WarpDL is installed correctly, the command will display the version number of the installed WarpDL.

## Verifying Signature

To ensure the integrity and authenticity of any released artifact, it is recommended to verify them using a public GPG key. Each release artifact is signed and accompanied by a corresponding signature file. These release artifacts can be found on the [Releases](https://github.com/warpdl/warp-releases/releases) page, providing assurance of their validity.

```bash
# fetch GPG signing key
gpg --keyserver keyserver.ubuntu.com --recv 9CAFFF2AC5F94C7C
# example: verify a release package
gpg --verify warp_0.0.27_linux_amd64.tar.gz.sig warp_0.0.27_linux_amd64.tar.gz || echo "Verification failed!"
```