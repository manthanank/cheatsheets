---
title: Create multiple Angular apps in one Angular app
date: "2023-03-19"
description: "multiple projects in one angular app."
tags: ["angular"]
---

Command to generate new new app in current app

```jsx
ng generate application app-name
```

To create multiple apps in one with clean structure

1. First new app with below command line

    ```jsx
    ng new app-name --create-application=false
    ```

2. Next create one more app in above app with this command

    ```jsx
    ng generate application app-name
    ```
