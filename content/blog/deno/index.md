---
title: Deno
date: "2023-01-05"
description: "Complete Deno Guide."
tags: ["deno"]
---

Installation

Using Shell (macOS and Linux):

```bash
curl -fsSL https://deno.land/x/install/install.sh | sh
```

Using PowerShell (Windows):

```bash
irm https://deno.land/install.ps1 | iex
```

Using [Scoop](https://scoop.sh/) (Windows):

```bash
scoop install deno
```

Using [Chocolatey](https://chocolatey.org/packages/deno) (Windows):

```bash
choco install deno
```

Using [Homebrew](https://formulae.brew.sh/formula/deno) (macOS):

```bash
brew install deno
```

Using [Nix](https://nixos.org/download.html) (macOS and Linux):

```bash
nix-shell -p deno
```

Build and install from source using [Cargo](https://crates.io/crates/deno):

```bash
cargo install deno --locked
```

To check version :

```bash
deno --version
```

To Update  :

```bash
deno upgrage

#For Specific Version
deno upgrade --version 1.0.1
```