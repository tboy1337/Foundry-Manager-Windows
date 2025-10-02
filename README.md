# Foundry Manager for Windows

<div align="center">

![Foundry](https://img.shields.io/badge/Foundry-Latest-blue?style=for-the-badge&logo=ethereum)
![Windows](https://img.shields.io/badge/Windows-10%2F11-0078D6?style=for-the-badge&logo=windows)
![License](https://img.shields.io/badge/License-CRL-orange?style=for-the-badge)

**A robust, automated installer and manager for [Foundry](https://github.com/foundry-rs/foundry) on Windows**

[Features](#features) • [Installation](#installation) • [Usage](#usage) • [Uninstall](#uninstall) • [Troubleshooting](#troubleshooting)

</div>

---

## Overview

Foundry Manager for Windows provides a seamless, one-click solution to install, update, and manage Foundry on Windows systems. No more manual downloads, path configurations, or version juggling—just run the script and start building.

### What is Foundry?

Foundry is a blazing fast, portable, and modular toolkit for Ethereum application development written in Rust. It consists of:

- **Forge** - Ethereum testing framework
- **Cast** - Swiss army knife for interacting with EVM smart contracts
- **Anvil** - Local Ethereum node
- **Chisel** - Fast, utilitarian, and verbose Solidity REPL

- **Foundry Official**: https://github.com/foundry-rs/foundry
- **Foundry Documentation**: https://getfoundry.sh/

## Features

### Installation Script (`install_foundry.cmd`)

- **Automatic Version Detection** - Fetches and installs the latest Foundry release automatically
- **Intelligent Updates** - Detects existing installations and upgrades safely
- **Safe Rollback** - Automatically backs up your current installation before upgrading
- **PATH Management** - Automatically adds Foundry to your user PATH
- **Comprehensive Error Handling** - Robust error checking with detailed feedback
- **Verification** - Validates installation integrity at every step
- **No Admin Required** - Runs with normal user privileges
- **Interactive Progress** - Clear, informative output throughout the process

### Uninstallation Script (`uninstall_foundry.cmd`)

- **Clean Removal** - Completely removes Foundry from your system
- **Process Management** - Automatically terminates running Foundry processes
- **PATH Cleanup** - Removes Foundry from your environment variables
- **Safety Confirmation** - Prompts for confirmation before uninstalling
- **Comprehensive Cleanup** - Removes all executables and installation directories

## Requirements

- **Operating System**: Windows 10 or Windows 11
- **Tools**: 
  - `curl` (built-in on Windows 10 version 1803 and later)
  - PowerShell 5.1 or later (included with Windows)
- **Permissions**: Normal user account (no administrator privileges needed)
- **Internet Connection**: Required for downloading Foundry

## Installation

### Quick Start

1. **Download this repository**
   ```cmd
   git clone https://github.com/tboy1337/Foundry-Manager-Windows.git
   cd Foundry-Manager-Windows
   ```

2. **Run the installer**
   ```cmd
   install_foundry.cmd
   ```

3. **Wait for completion**
   - The script will automatically detect the latest version
   - Download and extract Foundry
   - Install all components (forge, cast, anvil, chisel)
   - Update your PATH

4. **Restart your terminal**
   - Close and reopen your terminal/IDE to use Foundry commands

## Usage

### Installing/Updating Foundry

Simply run the installation script whenever you want to install or update Foundry:

```cmd
install_foundry.cmd
```

The script will:
- Check if you have Foundry installed
- Compare your version with the latest available
- Automatically upgrade if a newer version is available
- Skip installation if you're already up to date

### Verifying Installation

After installation, verify Foundry is working:

```cmd
forge --version
cast --version
anvil --version
chisel --version
```

## Uninstall

To completely remove Foundry from your system:

1. **Run the uninstaller**
   ```cmd
   uninstall_foundry.cmd
   ```

2. **Confirm removal**
   - The script will display your current version
   - Type `Y` to confirm uninstallation

3. **Restart your terminal**
   - Close and reopen your terminal/IDE to apply PATH changes

The uninstaller will:
- Terminate any running Foundry processes
- Remove all Foundry executables
- Clean up the installation directory
- Remove Foundry from your PATH

## Installation Directory

Foundry is installed to:
```
%LOCALAPPDATA%\Programs\Foundry\bin
```

## Troubleshooting

### Common Issues

#### "curl is not installed or in PATH"

**Solution**: Ensure you're running Windows 10 version 1803 or later. If curl is missing, download and install it from [curl.se](https://curl.se/windows/).

#### "Failed to download Foundry"

**Possible causes:**
- Network connectivity issues
- GitHub is temporarily unavailable
- Firewall/antivirus blocking the download

**Solution**: Check your internet connection and try again. You may need to temporarily disable your firewall/antivirus.

#### Commands not recognized after installation

**Solution**: Restart your terminal or IDE. If the issue persists, manually verify that `%LOCALAPPDATA%\Programs\Foundry\bin` is in your PATH:

```powershell
$env:Path -split ';' | Select-String "Foundry"
```

## What Gets Installed

The installer downloads and installs these Foundry components:

| Tool | Description |
|------|-------------|
| **forge** | Build, test, fuzz, debug, and deploy Solidity contracts |
| **cast** | Perform Ethereum RPC calls from the command line |
| **anvil** | Local Ethereum node for development and testing |
| **chisel** | Solidity REPL for quick testing and debugging |

## How It Works

### Key Safety Features

1. **Backup Before Upgrade** - Your current installation is backed up before any changes
2. **Integrity Checks** - Downloaded files are verified before extraction
3. **Safe Failure** - All errors are caught and handled gracefully

## License

This project is licensed under the CRL License - see [LICENSE.md](LICENSE.md) for details.

---

<div align="center">

**Made with ❤️ for the Ethereum development community**

*Happy building!* 🚀

</div>
