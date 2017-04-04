# api documentation for  [striptags (v3.0.1)](https://github.com/ericnorris/striptags)  [![npm package](https://img.shields.io/npm/v/npmdoc-striptags.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-striptags) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-striptags.svg)](https://travis-ci.org/npmdoc/node-npmdoc-striptags)
#### PHP strip_tags in Node.js

[![NPM](https://nodei.co/npm/striptags.png?downloads=true)](https://www.npmjs.com/package/striptags)

[![apidoc](https://npmdoc.github.io/node-npmdoc-striptags/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-striptags_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-striptags/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-striptags/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-striptags/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Eric Norris",
        "url": "https://github.com/ericnorris"
    },
    "bugs": {
        "url": "https://github.com/ericnorris/striptags/issues"
    },
    "dependencies": {},
    "description": "PHP strip_tags in Node.js",
    "devDependencies": {
        "istanbul": "^0.4.5",
        "mocha": "^3.2.0"
    },
    "directories": {},
    "dist": {
        "shasum": "48f0d6932549c47bb3582920c87527cf49a160c1",
        "tarball": "https://registry.npmjs.org/striptags/-/striptags-3.0.1.tgz"
    },
    "gitHead": "742795158765afe0bbcd7fe34739739cf0da1325",
    "homepage": "https://github.com/ericnorris/striptags",
    "keywords": [
        "striptags",
        "strip_tags",
        "html",
        "strip",
        "tags"
    ],
    "license": "MIT",
    "main": "src/striptags.js",
    "maintainers": [
        {
            "name": "ericnorris",
            "email": "erictnorris@gmail.com"
        }
    ],
    "name": "striptags",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/ericnorris/striptags.git"
    },
    "scripts": {
        "coverage": "istanbul cover _mocha -- -R spec",
        "test": "mocha"
    },
    "version": "3.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module striptags](#apidoc.module.striptags)
1.  [function <span class="apidocSignatureSpan">striptags.</span>init_streaming_mode (allowable_tags, tag_replacement)](#apidoc.element.striptags.init_streaming_mode)



# <a name="apidoc.module.striptags"></a>[module striptags](#apidoc.module.striptags)

#### <a name="apidoc.element.striptags.init_streaming_mode"></a>[function <span class="apidocSignatureSpan">striptags.</span>init_streaming_mode (allowable_tags, tag_replacement)](#apidoc.element.striptags.init_streaming_mode)
- description and source-code
```javascript
function init_striptags_stream(allowable_tags, tag_replacement) {
    allowable_tags  = allowable_tags || [];
    tag_replacement = tag_replacement || '';

    let context = init_context(allowable_tags, tag_replacement);

    return function striptags_stream(html) {
        return striptags_internal(html || '', context);
    };
}
```
- example usage
```shell
...
 sit amet
'''

## Streaming Mode
'striptags' can also operate in streaming mode. Simply call 'init_streaming_mode' to get back a function that accepts HTML and outputs
 stripped HTML. State is saved between calls so that partial HTML can be safely passed in.

'''javascript
let stream_function = striptags.init_streaming_mode(
    allowed_tags,
    tag_replacement
);

let partial_text = stream_function(partial_html);
let more_text    = stream_function(more_html);
'''
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
