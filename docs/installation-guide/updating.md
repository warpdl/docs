---
sidebar_position: 3
---

# Updating WarpDL

This document provides instructions on updating the Warp Download Manager using various package managers, as well as manually updating by replacing the installed binaries. By following these steps, you can ensure that you have the latest version of WarpDL with all the latest features and bug fixes.

## Updating WarpDL with Package Managers

### Brew (macOS)

To update WarpDL using Snap, follow these steps:

1. Open a terminal window.
2. Run the following command to update WarpDL:
```bash
brew upgrade warpdl
```
3. Once the update is complete, the WarpDL installation will be up-to-date.

### Snap Package Manager

To update WarpDL using Snap, follow these steps:

1. Open a terminal window.
2. Run the following command to update WarpDL:
```bash
sudo snap refresh warpdl
```
3. Enter your password if prompted, and confirm the update.
4. Once the update is complete, the WarpDL installation will be up-to-date.

### Scoop Package Manager (Windows)

To update WarpDL using Scoop, follow these steps:

1. Open a command prompt or PowerShell window.
2. Run the following command to update WarpDL:
```bash
scoop update warpdl
```
3. Once the update is complete, the WarpDL installation will be up-to-date.

### APT Package Manager (Debian/Ubuntu)

To update WarpDL using APT, follow these steps:

1. Open a terminal window.
2. Update the package lists by running the following command:
```bash
sudo apt-get update
```
3. Upgrade WarpDL by executing the following command:
```bash
sudo apt-get upgrade warpdl
```
4. Enter your password if prompted, and confirm the update.
5. Once the update is complete, the WarpDL installation will be up-to-date.

### Yum (RedHat/CentOS)

To update WarpDL using Yum, follow these steps:

1. Open a terminal window.
2. Run the following command to update WarpDL:
```bash
sudo yum update warp
```
3. Once the update is complete, the WarpDL installation will be up-to-date.

## Manual Update by Replacing Binaries

If you have installed WarpDL manually or the package manager update is not available, you can update it by replacing the installed binaries. Follow these steps to manually update WarpDL:

1. Visit the official [Releases](https://github.com/warpdl/warp-releases/releases/latest) page.
2. Choose the appropriate version of WarpDL for your operating system.
3. Download the latest version of WarpDL and save it to a location on your system.
4. Locate the existing WarpDL installation directory on your system.
5. Replace the existing WarpDL binaries with the newly downloaded ones.
6. Ensure that the file permissions and executable flags are correctly set for the updated binaries.
7. Once the replacement is complete, the WarpDL installation will be updated to the latest version.

## Verifying the Update

To verify that the WarpDL update was successful, open a command-line interface (CLI) and run the following command:

```bash
warpdl --version
```

If the update was completed successfully, the command will display the updated version number of WarpDL.

## Conclusion

By following the appropriate update method, either through package managers or manual replacement of binaries, you can keep your WarpDL installation up-to-date with the latest features and improvements. Enjoy using the latest version of WarpDL for fast and efficient file downloads!