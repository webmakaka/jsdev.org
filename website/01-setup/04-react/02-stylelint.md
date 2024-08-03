---
layout: page
title: Stylelint
description: Stylelint
keywords: env, react, stylelint
permalink: /setup/react/stylelint/
---

# Stylelint

**UPD:**

https://github.com/alexey-goloburdin/frontend-project-example/blob/main/.stylelintrc.json

<br/>

```
$ yarn add --dev stylelint stylelint-config-standard stylelint-order stylelint-order-config-standard stylelint-config-prettier
```

<br/>

**.stylelintrc.json**

<br/>

```json
{
  "extends": [
    "stylelint-config-standard",
    "stylelint-config-prettier",
    "stylelint-order-config-standard"
  ],
  "plugins": ["stylelint-order"],
  "rules": {
    "color-hex-case": "upper"
  }
}
```

<br/>

```
$ vi .stylelintignore
```

<br/>

```
node_modules
bin
*.*
!*.css
!*.scss
```

<br/>

**package.json**

<br/>

```json
***
"stylelint": "stylelint \"**/*.css\" --fix",
***
```

<br/>

```
// Check
$ npm stylelint src
```
