---
title: Node.js with Typescript
date: "2023-01-04"
description: "Nodejs with Typescript."
tags: ["nodejs", "typescript"]
---
Initialize and Install Typescript

```jsx
npm init -y
npm install -D typescript @types/node
```

Update the `package.json` with a build script and change the type to module.

```jsx
{
  "type": "module",
  "scripts": {
    "build": "tsc"
  },
}
```

Create a `tsconfig.json` file and use the **`NodeNext`** option to handle ES Modules with interop between CommonJS modules.

```typescript
{
    "compilerOptions": {
      "module": "NodeNext",
      "moduleResolution": "NodeNext",
      "target": "ES2020",
      "sourceMap": true,
      "outDir": "dist",
    },
    "include": ["src/**/*"],
  }
```

Use ES Modules

```jsx
//hello.ts
export const hello = 'Hello World!';

//index.ts
import { hello } from './hello.js';
```

Use CommonJS Modules

```jsx
//hello.cts
module.exports = 'Hey!';

//index.ts
import hola from './hello.cjs';
```

Next run

```jsx
npm run build
node dist/index.js
```
