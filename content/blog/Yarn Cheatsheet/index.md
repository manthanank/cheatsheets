---
title: Yarn Cheatsheet
date: "2022-11-28"
description: "Complete Yarn Guide."
---

## Installation

Install via npm:

```bash
npm install --global yarn
```

Check installation:

```bash
yarn --version
```

## Project Initialization

Starting a new project:

```bash
yarn init
```

## Managing Dependencies

### Adding a Dependency

```bash
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

### Adding to Different Categories

Add to `devDependencies`, `peerDependencies`, and `optionalDependencies` respectively:

```bash
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```

### Upgrading a Dependency

```bash
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

### Removing a Dependency

```bash
yarn remove [package]
```

## Installing Dependencies

Install all the dependencies of the project:

```bash
yarn install
```

or simply:

```bash
yarn
```

## Running Scripts

Add scripts in `package.json`:

```json
{
  "scripts": {
    "start": "node index.js"
  }
}
```

Run the script:

```bash
yarn start
```
