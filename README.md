cert-info.js
============

Read basic info from a cert.pem / x509 certificate.

Install
=======

```bash
# bin
npm install --global certpem

# node.js library
npm install --save certpem
```

Usage
=====

For basic info (subject, altnames, issuedAt, expiresAt):

```bash
certpem /path/to/cert.pem
```

Output all info by passing `--debug` or use `--json` to see the basic info pretty-printed.

```javascript
'use strict';

var certpem = require('certpem').certpem
var cert = fs.readFile('cert.pem', 'ascii', function (err, certstr) {
  console.info(cert.pem.info());

  console.info(cert.pem.debug());
});
```

```javascript
{
  "subject": "localhost.daplie.com",
  "altnames": [
    "localhost.daplie.com"
  ],
  "issuedAt": 1465516800000,
  "expiresAt": 1499731199000
}
```
