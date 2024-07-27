---
title: Cloudinary Cheatsheet
date: "2023-01-04"
description: "Cloudinary."
---

**Install and configure the SDK in your application code** -

JavaScript

```bash
npm install cloudinary-core --save
```

```jsx
var cl = new cloudinary.Cloudinary({cloud_name: "dm2i0nggm", secure: true});
```

Node.js

```bash
npm install cloudinary
```

```jsx
cloudinary.config({ 
  cloud_name: 'dm2i0nggm', 
  api_key: '316443853788968', 
  api_secret: 'aMTulyDCA1d7gIg7LiFOjbaRAVc' 
});
```

React

```bash
npm install cloudinary-react --save
```

```jsx
<CloudinaryContext cloudName="dm2i0nggm">
  <div>
    <Image publicId="sample" width="50" />
  </div>
  <Image publicId="sample" width="0.5" />
</CloudinaryContext>
```

Angular

```bash
bower install cloudinary_ng#1.x --save
```

```tsx
yourApp.config(['cloudinaryProvider', function (cloudinaryProvider) {
  cloudinaryProvider
      .set("cloud_name", "dm2i0nggm")
      .set("secure", true)
      .set("upload_preset", "my_preset");
}]);
```
