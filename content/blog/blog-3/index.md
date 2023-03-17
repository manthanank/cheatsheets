---
title: Add package manager to Angular app
date: "2023-03-17"
description: "package manager in angular app."
tags: ["angular"]
---

Adding `packageManager` in `angular.sjon`

```tsx
{
    "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
    "version": 1,
    "newProjectRoot": "projects",
    "projects" {
        ...
    },
    "cli": {
        "packageManager": "npm" // either select yarn, npm, pnpm or cnpm
    }
}
```
