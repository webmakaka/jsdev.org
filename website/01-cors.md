---
layout: page
title: Cors
description: Cors
keywords: Cors
permalink: /cors/
---

# No 'Access-Control-Allow-Origin' header is present on the requested resource.

Origin 'http://localhost:8080' Is therefore not allowed access.

<br/>

# Cors

    $ cd /project/server/
    $ npm install --save cors

<br/>

    $ vi app.js

    const cors = require('cors');
    app.use(cors());

<br/>
    -- or assign host
    app.use(cors({ origin: 'http://localhost:8080' }));
