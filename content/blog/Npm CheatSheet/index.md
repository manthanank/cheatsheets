---
title: NPM CheatSheet
date: "2024-11-07"
description: "Complete NPM Guide."
---

## Resources

- [NPM Documentation](https://docs.npmjs.com/)
- [NPM CLI Commands](https://docs.npmjs.com/cli/v8/commands)

## Installation

Install via Node.js:

```bash
npm install --global npm
```

Check installation:

```bash
npm --version
```

## Usage

Initialize a new project:

```bash
npm init
```

Install a package:

```bash
npm install <package-name>
```

Install a package as a development dependency:

```bash
npm install --save-dev <package-name>
```

Install a package globally:

```bash
npm install --global <package-name>
```

Update a package:

```bash
npm update <package-name>
```

Remove a package:

```bash
npm uninstall <package-name>
```

## Commands

- `npm init`: Initialize a new project.
- `npm install <package>`: Install a package.
- `npm install --save-dev <package>`: Install a package as a development dependency.
- `npm install --global <package>`: Install a package globally.
- `npm update <package>`: Update a package.
- `npm uninstall <package>`: Remove a package.

## Example

```bash
npm install lodash
npm install --save-dev jest
npm install --global nodemon
npm update lodash
npm uninstall lodash
```

## Configuration

Create a `package.json` file:

```bash
npm init --yes
```

Set the registry:

```bash
npm config set registry https://registry.npmjs.org/
```

Check the registry:

```bash
npm config get registry
```

## Scripts

Add a script to `package.json`:

```json
"scripts": {
  "start": "node index.js"
}
```

Run a script:

```bash
npm run start
```

## Versioning

Check the version of a package:

```bash
npm show <package-name> version
```

Check outdated packages:

```bash
npm outdated
```

Update all packages:

```bash
npm update
```

## Publishing

Login to NPM:

```bash
npm login
```

Publish a package:

```bash
npm publish
```

Update the package version:

```bash
npm version <update_type>
```

## Troubleshooting

Clear the cache:

```bash
npm cache clean --force
```

Check for vulnerabilities:

```bash
npm audit
```

Fix vulnerabilities:

```bash
npm audit fix
```
