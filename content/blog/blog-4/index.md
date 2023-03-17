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

- First new app with below command line

    ```jsx
    ng new app-name --create-application=false
    ```

- Next create one more app in above app with this command

    ```jsx
    ng generate application app-name
    ```
