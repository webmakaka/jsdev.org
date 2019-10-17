---
layout: page
title: Atom (IDE) Plugins
permalink: /env/ide/atom/plugins/
---

# Atom (IDE) Plugins

<br/>

### Additional Packages:

Edit --> Preferences --> Install

or

    $ apm install autosave
    $ apm install atom-beautify

HTML and CSS

    $ apm install emmet

MarkDown

    $ apm install inline-markdown-images

For JavaScript:

    $ apm install jshint

For TwitterBootstrap (https://atom.io/packages/atom-bootstrap4):

    $ apm install atom-bootstrap4

For React:

    $ apm install react

For Angular 2:

    $ apm install atom-typescript

Terminal:

    $ apm install terminal-plus

<br/>

**Top 5 Packages: Atom Code Editor**

<br/><br/>

<div align="center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/DmKNDxlNLoE" frameborder="0" allowfullscreen></iframe>
</div>

<br/>

    5) joke
    4) emmet https://github.com/emmetio/emmet-atom
    3) terminal plus https://atom.io/packages/terminal-plus
    2) Minimap
    1) Atom Bootstrap 4 https://atom.io/packages/atom-bootstrap4

<br/>

### Installed by me packages

    $ apm list --installed --bare
    atom-beautify@0.29.7
    atom-typescript@8.9.1
    inline-markdown-images@1.0.0
    jshint@1.8.5
    linter@1.11.4
    react@0.15.0

<br/>

list of all packages

    $ apm list -ib | sed s/@.*//
    atom-beautify
    atom-typescript
    inline-markdown-images
    jshint
    linter
    react

<br/>

the same, excluding disabled packages

    $ apm list -ibd false | sed s/@.*//

<br/>

**disable package (I didn't check it)**

    $(apm list --installed --bare)
    $ apm disable package_name

<br/>

### Emmet For Fast HTML & CSS

Atom Editor Tutorials #10 - Emmet For Fast HTML & CSS
https://www.youtube.com/watch?v=BQurqKG6nGY

http://docs.emmet.io/cheat-sheet/

<br/>

### inline-markdown-images

    $ apm install inline-markdown-images

![inline-markdown-images](http://raw.githubusercontent.com/some-atom/inline-markdown-images/master/preview.gif)

<br/>

### Editor Config

https://github.com/sindresorhus/atom-editorconfig#readme

    $ apm install editorconfig

<br/>

Put .editorconfig into root of project

<br/>

    # editorconfig.org
    root = true

    [*]
    indent_style = space
    indent_size = 2
    end_of_line = lf
    charset = utf-8
    trim_trailing_whitespace = true
    insert_final_newline = true

    [*.md]
    trim_trailing_whitespace = false

<!-- <br/>

### tabs-to-spaces (Deprecated for my)


    $ apm install tabs-to-spaces

    tabs-to-spaces:untabify

More Info:
https://atom.io/packages/tabs-to-spaces -->

<br/>

### split-diff

<br/>

### Atom Eslint plugin (First Try)

    $ apm install linter-eslint

<br/>

    $ npm install --save-dev eslint [eslint-plugins]

    $ npm install -g eslint [eslint-plugins]

<br/>

    $ eslint --init

<br/>

### Remove trailing whitespace on save (Need for Jade Templates for example)

Edit --> Preferences go to Packages tab and search for whitespace.  
Click on the whitespace package and uncheck Remove Trailing Whitespace option.
