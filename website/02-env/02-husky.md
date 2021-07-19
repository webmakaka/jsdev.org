---
layout: page
title: Run checks before commit (lint-staged husky)
description: Run checks before commit (lint-staged husky)
keywords: husky
permalink: /env/husky/
---

<br/>

# Run checks before commit (lint-staged husky)

```bash
$ yarn add -D lint-staged husky
```

<br/>

**package.json**

<!--

  "scripts": {
    ******
    "precommit": "lint-staged"
  },
  "devDependencies": {
    ********
  },

-->

```json
"lint-staged": {
  "*.{js, jsx}": ["node_modules/.bin/eslint --max-warnings=0", "prettier --write", "git add"]
}
```

<br/>

**.huskyrc.json**

```
{
  "hooks": {
    "pre-commit": "lint-staged",
    "pre-push": "npm run test"
  }
}
```
