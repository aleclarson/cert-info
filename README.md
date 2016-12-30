<!-- AD_TPL_BEGIN -->

About Daplie: We're taking back the Internet!
--------------

Down with Google, Apple, and Facebook!

We're re-decentralizing the web and making it read-write again - one home cloud system at a time.

Tired of serving the Empire? Come join the Rebel Alliance:

<a href="mailto:jobs@daplie.com">jobs@daplie.com</a> | [Invest in Daplie on Wefunder](https://daplie.com/invest/) | [Pre-order Cloud](https://daplie.com/preorder/), The World's First Home Server for Everyone

<!-- AD_TPL_END -->

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

CLI
---

For basic info (subject, altnames, issuedAt, expiresAt):

```bash
certpem /path/to/cert.pem
```

Output all info by passing `--debug` or use `--json` to see the basic info pretty-printed.

node.js
-------

```javascript
'use strict';

var certpem = require('certpem').certpem
var cert = fs.readFile('cert.pem', 'ascii', function (err, certstr) {

  // basic info
  console.info(certpem.info(certstr));

  // way too much info
  console.info(certpem.debug(certstr));

});
```

Example output:

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

With a few small changes this could also work in the browser (that's how its dependencies are designed).
