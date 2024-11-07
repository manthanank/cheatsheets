---
title: Nvm CheatSheet
date: "2023-01-05"
description: "Complete Nvm Guide."
---

## Resources

- [NVM for Windows GitHub](https://github.com/coreybutler/nvm-windows)
- [Releases · coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows/releases)
- Download: **[nvm-setup.exe](https://github.com/coreybutler/nvm-windows/releases/download/1.1.9/nvm-setup.exe)**

## Installation

1. Download the setup file from the link above.
2. Run the installer as an administrator.

## Usage

Open Command Prompt as an administrator and use the following commands:

```bash
# List available versions
nvm ls available

# Install a specific version
nvm install <version-name>

# Use a specific version
nvm use <version-name>

# Check the current version
nvm current

# Uninstall a specific version
nvm uninstall <version-name>
```

## Commands

- `nvm list`: List installed versions.
- `nvm list available`: List available versions.
- `nvm install <version>`: Install a specific version.
- `nvm use <version>`: Use a specific version.
- `nvm current`: Check the current version.
- `nvm uninstall <version>`: Uninstall a specific version.

## Example

```bash
nvm install 14.17.0
nvm use 14.17.0
```
