---
title: Yarn Cheatsheet
date: "2022-11-28"
description: "Complete Yarn Guide."
---

Install via npm

```jsx
npm install --global yarn
```

Check installation

```jsx
yarn --version
```

Starting a new project

```jsx
yarn init
```

Adding a dependency

```jsx
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

Adding a dependency to different categories of dependencies

Add to `devDependencies`, `peerDependencies`, and `optionalDependencies` respectively:

```jsx
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```

Upgrading a dependency

```jsx
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

Removing a dependency

```jsx
yarn remove [package]
```

Installing all the dependencies of project

```jsx
yarn

or

yarn install
```
