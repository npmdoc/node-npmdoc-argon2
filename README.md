# npmdoc-argon2

#### basic api documentation for  [argon2 (v0.15.0)](https://github.com/ranisalt/node-argon2#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-argon2.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-argon2) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-argon2.svg)](https://travis-ci.org/npmdoc/node-npmdoc-argon2)

#### An Argon2 library for Node

[![NPM](https://nodei.co/npm/argon2.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/argon2)

- [https://npmdoc.github.io/node-npmdoc-argon2/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-argon2/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-argon2/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-argon2/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Ranieri Althoff"
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
            "name": "ranisalt"
        }
    ],
    "name": "argon2",
    "optionalDependencies": {},
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
    },
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
