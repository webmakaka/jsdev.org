---
layout: page
title: Postma
description: Postma
keywords: Postman
permalink: /testing/postman/
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
pm.test('Status is ok, respnse is json', () => {
  const access_token = pm.globals.get('access_token');

  pm.response.to.have.status(200);
  pm.response.to.be.ok;
  pm.response.to.json;

  pm.expect(access_token).to.not.be.null;
});
```
