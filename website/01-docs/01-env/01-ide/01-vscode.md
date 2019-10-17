---
layout: page
title: JavaScript IDE - Visual Studio Code (Microsoft)
permalink: /env/ide/vscode/
---

# Visual Studio Code (Microsoft)

code.visualstudio.com

Add ESLint & Prettier to VS Code for a Create React App  
https://www.youtube.com/watch?v=bfyI9yl3qfE

<br/>

**Visual Studio Code Settings:**

minimal

```
{
  "editor.fontSize": 26,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "terminal.integrated.fontSize": 26,
  "editor.formatOnSave": true,
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 10000,
  "eslint.enable": true
}
```

<br/>

**additional:**

    {
        "emmet.includeLanguages": {
            "javascript": "javascriptreact"
        },
        "emmet.syntaxProfiles": {
            "javascript": "jsx",
            "javascript": "html"
        }
    }

<br/>

**Visual Studio Code Plugins:**

- ESLint
- Prettier - Code formatter
- GitLens
- Bracket Pair Colorizer
- Live Server
- Node.js Modules Intellisense

<!--
Highlight Matching Tag
-->

<br/>

**React:**

- Simple React Snippets
- ES7 React/Redux/React-Native/JS snippets

<br/>

**Vue:**

- Vetur

<br/>

**GraphQL:**

- GraphQL for VSCode (Kumar)

<br/>

**Docker:**

- docker

<br/>

### Eslint

    # npm install -g eslint \
    eslint-plugin-standard \
    eslint-plugin-import \
    eslint-plugin-node \
    eslint-plugin-promise

<br/>

    # npm install -g eslint-config-standard

<br/>

    # ls /usr/local/lib/node_modules/
    eslint                  eslint-plugin-import  eslint-plugin-promise   npx
    eslint-config-standard  eslint-plugin-node    eslint-plugin-standard

<br/>

### + JSon formatter plugin for chrom
