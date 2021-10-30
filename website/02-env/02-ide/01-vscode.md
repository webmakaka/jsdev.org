---
layout: page
title: JavaScript IDE - Visual Studio Code, VSCODE (Microsoft)
description: JavaScript IDE - Visual Studio Code (Microsoft)
keywords: env, ide, vscode, Microsoft, JavaScript
permalink: /env/ide/vscode/
---

# Visual Studio Code (Microsoft)

code.visualstudio.com

**Add ESLint & Prettier to VS Code for a Create React App**  
https://www.youtube.com/watch?v=bfyI9yl3qfE

<br/>

**Visual Studio Code Settings:**

<!--

minimal

```
{
  "editor.wordWrap": "on",
  "terminal.integrated.fontSize": 26,
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

-->

<br/>

**Visual Studio Code Plugins:**

- ESLint (Dirk Baeumer)
- stylelint (vscode-stylelint)
- Prettier - Code formatter (ext install esbenp.prettier-vscode)
- GitLens
- Bracket Pair Colorizer
- Auto Rename Tag
- CSS Peek
- Code Spell Checker
- Visual Studio IntelliCode
- Inline Parameters for VSCode
- Color Highlight (Sergii Naumov)
- Highlight Matching Tag

**Snippets:**

- ES7 React/Redux/GraphQL/React-Native snippets - dsznajder
- JavaScript (ES6) code snippets

<br/>

**Visual Studio Themes:**

- Monokai Pro (Will ask money!)

<br/>

<!--

    $ cd ~/.vscode/extensions/monokai.theme-monokai-pro-vscode-1.1.19/
    $ code /js/app.js

    beatify

Find key: "isValidLicense",

Change return statement

Было в старых

```
return !(!e || !t) && t === (0, n.default)("" + a.default.APP.UUID + e).match(/.{1,5}/g).slice(0, 5).join("-")
```

Стало

```
            {
              key: 'isValidLicense',
              value: function () {
                var e =
                    arguments.length > 0 && void 0 !== arguments[0]
                      ? arguments[0]
                      : '',
                  t =
                    arguments.length > 1 && void 0 !== arguments[1]
                      ? arguments[1]
                      : '';
                if (!e || !t) return !1;
                var o = s()(''.concat(i.APP.UUID).concat(e)),
                  r = o.match(/.{1,5}/g),
                  n = r.slice(0, 5).join('-');
                return t === n;
              },
            },

```

to

```
return true
```

-->

<br/>

**Visual Studio Themes:**

CTRL + P

> Preferences: Open Settings (JSON)

```js
{
    "explorer.compactFolders": false,
    "editor.fontSize": 22,
    "files.autoSave": "afterDelay",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.organizeImports": true
    },
    "prettier.requireConfig": true,
    "editor.tabSize": 2,
    "workbench.iconTheme": "Monokai Pro (Filter Spectrum) Icons",
    "workbench.colorTheme": "Monokai Pro (Filter Spectrum)",
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "typescript.preferences.importModuleSpecifier": "non-relative",
    "javascript.preferences.importModuleSpecifier": "non-relative"
}
```

<!--

<br/>

**Possible can be interesting :**

- TypeScript Hero
- TypeScript Importer

-->

<br/>

**React:**

- Reactjs code snippets (publisher:"charalampos karypidis" (My Favourite))

or

- Simple React Snippets

or

- ES7 React/Redux/GraphQL/React-Native snippets

<br/>

**Tailwind**

- Tailwind CSS IntelliSense
- Headwind (Ryan Heybourn)

<br/>

**Vue:**

- Vetur

<br/>

**GraphQL:**

- GraphQL for VSCode (Kumar)
- Apollo GraphQL

<br/>

**Docker:**

- Docker (MicroSoft)

<br/>

**Format on save document (same in the JSON config file)**

VSCode --> Preverences --> Extensions --> install --> Prettier - Code formatter esbenp.prettier-vscode

VSCode --> File --> Preverences --> Settings:

- Format on Save (checked)
- Prettier Require Config --> require a prettier configuration file to foramt (checked)

<br/>

### <a href="/env/prettier/">Prettier</a>
