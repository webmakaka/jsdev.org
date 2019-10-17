---
layout: page
title: Install Atom on Ubuntu 14.04
permalink: /env/ide/atom/install-atom-on-ubuntu-14-04/
---

# Install Atom on Ubuntu 14.04

    $ sudo add-apt-repository -y ppa:webupd8team/atom
    $ sudo apt-get update -y
    $ sudo apt-get install -y atom

<br/>

More information you can find on:
http://www.webupd8.org/2014/05/install-atom-text-editor-in-ubuntu-via-ppa.html

<br/>

### Additional setup:

**Make brackets more visible**

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
