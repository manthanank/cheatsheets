---
title: Configuring build cache in Angular App
date: "2023-03-17"
description: "build cache setup in angular app."
tags: ["angular"]
---

Adding `cache` in `anular.json`

```tsx
{
    "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
    "version": 1,
    "newProjectRoot": "projects",
    "projects" 
    {
        ...
    },
    "cli": {
        "cache": {
            "enabled": true, // select true or false
            "environment": "all", // select all, ci or local
            "path": "temp/cache/.angular" // folder name where it should add
        }
    }
}
```
