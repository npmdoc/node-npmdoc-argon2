# api documentation for  [argon2 (v0.15.0)](https://github.com/ranisalt/node-argon2#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-argon2.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-argon2) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-argon2.svg)](https://travis-ci.org/npmdoc/node-npmdoc-argon2)
#### An Argon2 library for Node

[![NPM](https://nodei.co/npm/argon2.png?downloads=true)](https://www.npmjs.com/package/argon2)

[![apidoc](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-argon2%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-argon2/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Ranieri Althoff",
        "email": "ranisalt+argon2@gmail.com"
    },
    "ava": {
        "files": [
            "test.js"
        ],
        "babel": "inherit",
        "require": [
            "babel-register"
        ]
    },
    "bugs": {
        "url": "https://github.com/ranisalt/node-argon2/issues"
    },
    "dependencies": {
        "any-promise": "^1.3.0",
        "bindings": "^1.2.1",
        "nan": "^2.4.0"
    },
    "description": "An Argon2 library for Node",
    "devDependencies": {
        "@types/node": "^6.0.42",
        "ava": "^0.17.0",
        "babel-cli": "^6.18.0",
        "babel-plugin-transform-async-to-generator": "^6.16.0",
        "babel-preset-es2015": "^6.18.0",
        "babel-register": "^6.18.0",
        "nyc": "^10.0.0",
        "object-assign": "^4.1.0",
        "sandra": "^0.1.0",
        "typescript": "^2.0.3",
        "xo": "^0.17.1"
    },
    "directories": {},
    "dist": {
        "shasum": "25cb766908c966d1372c4436d3336316b96b121e",
        "tarball": "https://registry.npmjs.org/argon2/-/argon2-0.15.0.tgz"
    },
    "engines": {
        "node": ">=4.0.0"
    },
    "gitHead": "df774605657afb899203fd25b3e20aa253423db3",
    "gypfile": true,
    "homepage": "https://github.com/ranisalt/node-argon2#readme",
    "keywords": [
        "argon2",
        "crypto",
        "encryption",
        "hashing",
        "password"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ranisalt",
            "email": "ranisalt@gmail.com"
        }
    ],
    "name": "argon2",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/ranisalt/node-argon2.git"
    },
    "scripts": {
        "benchmark": "babel-node benchmark.js",
        "clean": "node-gyp clean",
        "install": "node-gyp rebuild",
        "test": "tsc -p . && node test-d.js && xo && nyc --reporter=lcov ava"
    },
    "types": "index.d.ts",
    "version": "0.15.0",
    "xo": {
        "esnext": true,
        "rules": {
            "no-div-regex": "off",
            "prefer-const": "off"
        },
        "semicolon": false,
        "space": 2
    }
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module argon2](#apidoc.module.argon2)
1.  [function <span class="apidocSignatureSpan">argon2.</span>generateSalt (length)](#apidoc.element.argon2.generateSalt)
1.  [function <span class="apidocSignatureSpan">argon2.</span>hash (plain, salt, options)](#apidoc.element.argon2.hash)
1.  [function <span class="apidocSignatureSpan">argon2.</span>verify (hash, plain)](#apidoc.element.argon2.verify)
1.  number <span class="apidocSignatureSpan">argon2.</span>argon2d
1.  number <span class="apidocSignatureSpan">argon2.</span>argon2i
1.  number <span class="apidocSignatureSpan">argon2.</span>argon2id
1.  object <span class="apidocSignatureSpan">argon2.</span>defaults
1.  object <span class="apidocSignatureSpan">argon2.</span>limits



# <a name="apidoc.module.argon2"></a>[module argon2](#apidoc.module.argon2)

#### <a name="apidoc.element.argon2.generateSalt"></a>[function <span class="apidocSignatureSpan">argon2.</span>generateSalt (length)](#apidoc.element.argon2.generateSalt)
- description and source-code
```javascript
generateSalt(length) {
  return new Promise((resolve, reject) => {
    crypto.randomBytes(length || 16, (err, salt) => {
<span class="apidocCodeCommentSpan">      /* istanbul ignore if */
</span>      if (err) {
        reject(err)
      }
      resolve(salt)
    })
  })
}
```
- example usage
```shell
...
}
'''

You can provide your own salt as the second parameter. It is **highly**
recommended to use the salt generating methods instead of a hardcoded, constant
salt:
'''js
argon2.generateSalt().then(salt => {
  // ...
});

// ES7 or TypeScript

const salt = await argon2.generateSalt();
'''
...
```

#### <a name="apidoc.element.argon2.hash"></a>[function <span class="apidocSignatureSpan">argon2.</span>hash (plain, salt, options)](#apidoc.element.argon2.hash)
- description and source-code
```javascript
hash(plain, salt, options) {
  salt = new Buffer(salt)
  options = Object.assign({}, defaults, options)

  return validate(salt, options).then(() => new Promise((resolve, reject) => {
    bindings.hash(new Buffer(plain), salt, options, resolve, reject)
  }))
}
```
- example usage
```shell
...
cryptographically-safe salts. Salts **must** be at least 8-byte long buffers.

To hash a password:
'''js
const argon2 = require('argon2');
const salt = new Buffer('somesalt');

argon2.hash('password', salt).then(hash => {
  // ...
}).catch(err => {
  // ...
});

// ES7 or TypeScript
...
```

#### <a name="apidoc.element.argon2.verify"></a>[function <span class="apidocSignatureSpan">argon2.</span>verify (hash, plain)](#apidoc.element.argon2.verify)
- description and source-code
```javascript
verify(hash, plain) {
  if (!/^\$argon2(i|d|id)(\$v=\d+)?\$m=\d+,t=\d+,p=\d+(?:\$[\w+/]+){2}$/.test(hash)) {
    return Promise.reject(new Error('Invalid hash, must be in MCF, generated by Argon2.'))
  }

  return new Promise((resolve, reject) => {
    bindings.verify(new Buffer(hash), new Buffer(plain), resolve, reject)
  })
}
```
- example usage
```shell
...
'''js
console.log(argon2.defaults);
// => { timeCost: 3, memoryCost: 12, parallelism: 1, type: argon2.argon2i }
'''

To verify a password:
'''js
argon2.verify('<big long hash>', 'password').then(match => {
if (match) {
  // password match
} else {
  // password did not match
}
}).catch(err => {
// internal failure
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
