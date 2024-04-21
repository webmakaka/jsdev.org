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
- IntelliCode (Microsoft) (ext install VisualStudioExptTeam.vscodeintellicode)
- Inline Parameters for VSCode
- Color Highlight (Sergii Naumov)
- Highlight Matching Tag
- Trailing Spaces (Shardul Mahadik)

**Snippets:**

- ES7 React/Redux/GraphQL/React-Native snippets - dsznajder
- JavaScript (ES6) code snippets

<br/>

**Visual Studio Themes:**

- Monokai Pro (Will ask money!)

<br/>

<!--

    $ cd ~/.vscode/extensions/monokai.theme-monokai-pro-vscode-1.2.1/
    $ cp js/main.js js/main.js.orig
    $ code /js/main.js

https://beautifier.io/


Find key: "isValidLicense",

Change return statement



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

**Visual Studio:**

CTRL + SHIFT + P

> Preferences: Open User Settings (JSON)

```js
{
    "explorer.compactFolders": false,
    "editor.fontSize": 22,
    "files.autoSave": "afterDelay",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.organizeImports": "explicit"
    },
    "prettier.requireConfig": true,
    "editor.tabSize": 2,
    "workbench.iconTheme": "Monokai Pro (Filter Spectrum) Icons",
    "workbench.colorTheme": "Monokai Pro (Filter Spectrum)",
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "typescript.preferences.importModuleSpecifier": "non-relative",
    "javascript.preferences.importModuleSpecifier": "non-relative",
    "[prisma]": {
        "editor.defaultFormatter": "Prisma.prisma"
    },
    "[go]": {
        "editor.insertSpaces": true,
        "editor.formatOnSave": true,
        "editor.defaultFormatter": "golang.go"
    },
    "editor.stickyScroll.enabled": false,
}
```

<br/>

**Also could be added:**

```
"trailing-spaces.trimOnSave": true
```

<!--

<br/>

**Possible can be interesting :**

- TypeScript Hero
- TypeScript Importer

-->

<br/>

**TypeScript:**

- JavaScript and TypeScript Nightly (microsoft)

<br/>

**Angular:**

- Angular Language Service (From Angular Devs)

<br/>

**React:**

- ES7 React/Redux/GraphQL/React-Native snippets

<br/>

**Prisma**

- Prisma (prisma.io)

<br/>

**Tailwind**

- Tailwind CSS IntelliSense

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
