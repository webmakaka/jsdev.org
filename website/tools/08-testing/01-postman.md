---
layout: page
title: Postma
description: Postma
keywords: Postman
permalink: /tools/testing/postman/
---

# Postman

<br/>

### Authorization

```
Type: Bearer Token
Token: {{access_token}}
```

<br/>

### Pre-request Script

```js
const authorization = {
  method: 'POST',
  header: {
    Authorization: 'Basic Y2xpZW50OnNlY3JlXX==',
  },
  url: 'http://authserver',
};
pm.sendRequest(authorization, function (err, response) {
  // console.log('authorization');
  // console.log(response.json().access_token);
  // console.log('authorization');
  pm.globals.set('access_token', response.json().access_token);
});
```

<br/>

### Tests

```js
pm.test('Access Token is OK!', () => {
  const access_token = pm.globals.get('access_token');
  pm.expect(access_token).to.not.be.null;
});
```

```js
pm.test('Response is json', () => {
  pm.response.to.have.status(200);
  pm.response.to.be.ok;
  pm.response.to.json;
});
```
