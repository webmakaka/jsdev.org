---
layout: page
title: Stylelint
description: Stylelint
keywords: env, react, stylelint
permalink: /env/react/stylelint/
---

# Stylelint

<br/>

```
$ yarn add -D stylelint stylelint-config-standard stylelint-order stylelint-order-config-standard
```

<br/>

**.stylelintrc.json**

<br/>

```json
{
  "extends": ["stylelint-config-standard", "stylelint-order-config-standard"],
  "plugins": ["stylelint-order"],
  "rules": {
    "color-hex-case": "upper"
  }
}
```

<br/>

**package.json**

<br/>

```json
***
"stylelint": "stylelint \"**/*.css\" --fix",
***
```
