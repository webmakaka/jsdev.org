---
layout: page
title: Atom (IDE) How to Make brackets more visible
permalink: /env/ide/atom/how-to-make-brackets-more-visible/
---

# Atom (IDE) How to Make brackets more visible

    $ cd ~/.atom/
    $ cp styles.less styles.less.bkp

<br/>

File styles.less I replace on:

    $ vi styles.less

<br/>

    editor, atom-text-editor::shadow {

        .bracket-matcher {
            border-bottom: 1px solid lime;
            position: absolute;
            border: 1px solid rgba(0, 255, 0, 0.7);
            background-color: rgba(0, 255, 0, 0.3);
            border-radius: 32px
        }
    }
