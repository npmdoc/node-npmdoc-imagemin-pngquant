# api documentation for  [imagemin-pngquant (v5.0.0)](https://github.com/imagemin/imagemin-pngquant#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-imagemin-pngquant.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-imagemin-pngquant) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-imagemin-pngquant.svg)](https://travis-ci.org/npmdoc/node-npmdoc-imagemin-pngquant)
#### pngquant imagemin plugin

[![NPM](https://nodei.co/npm/imagemin-pngquant.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/imagemin-pngquant)

[![apidoc](https://npmdoc.github.io/node-npmdoc-imagemin-pngquant/build/screenCapture.buildCi.browser.apidoc.html.png)](https://npmdoc.github.io/node-npmdoc-imagemin-pngquant/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-imagemin-pngquant/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-imagemin-pngquant/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Kevin Mårtensson",
        "url": "github.com/imagemin"
    },
    "bugs": {
        "url": "https://github.com/imagemin/imagemin-pngquant/issues"
    },
    "dependencies": {
        "exec-buffer": "^3.0.0",
        "is-png": "^1.0.0",
        "pngquant-bin": "^3.0.0"
    },
    "description": "pngquant imagemin plugin",
    "devDependencies": {
        "ava": "*",
        "pify": "^2.3.0",
        "xo": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "7d72405778caba9c510eb3cb4590c8413383560e",
        "tarball": "https://registry.npmjs.org/imagemin-pngquant/-/imagemin-pngquant-5.0.0.tgz"
    },
    "engines": {
        "node": ">=4"
    },
    "files": [
        "index.js"
    ],
    "gitHead": "6c3631e6b3df5463a31a7fc48d418763c70cf22b",
    "homepage": "https://github.com/imagemin/imagemin-pngquant#readme",
    "keywords": [
        "compress",
        "image",
        "imageminplugin",
        "img",
        "minify",
        "optimize",
        "png",
        "pngquant"
    ],
    "license": "MIT",
    "maintainers": [
        {
            "name": "kevva"
        },
        {
            "name": "shinnn"
        },
        {
            "name": "sindresorhus"
        }
    ],
    "name": "imagemin-pngquant",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/imagemin/imagemin-pngquant.git"
    },
    "scripts": {
        "test": "xo && ava"
    },
    "version": "5.0.0",
    "xo": {
        "esnext": true
    }
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module imagemin-pngquant](#apidoc.module.imagemin-pngquant)
1.  [function <span class="apidocSignatureSpan"></span>imagemin-pngquant ({}, opts)](#apidoc.element.imagemin-pngquant.imagemin-pngquant)
1.  [function <span class="apidocSignatureSpan">imagemin-pngquant.</span>toString ()](#apidoc.element.imagemin-pngquant.toString)



# <a name="apidoc.module.imagemin-pngquant"></a>[module imagemin-pngquant](#apidoc.module.imagemin-pngquant)

#### <a name="apidoc.element.imagemin-pngquant.imagemin-pngquant"></a>[function <span class="apidocSignatureSpan"></span>imagemin-pngquant ({}, opts)](#apidoc.element.imagemin-pngquant.imagemin-pngquant)
- description and source-code
```javascript
opts => buf => {
	opts = Object.assign({}, opts);

	if (!Buffer.isBuffer(buf)) {
		return Promise.reject(new TypeError('Expected a buffer'));
	}

	if (!isPng(buf)) {
		return Promise.resolve(buf);
	}

	const args = [
		'--output', execBuffer.output,
		execBuffer.input
	];

	if (opts.floyd && typeof opts.floyd === 'number') {
		args.push('--floyd=${opts.floyd}');
	}

	if (opts.floyd && typeof opts.floyd === 'boolean') {
		args.push('--floyd');
	}

	if (opts.nofs) {
		args.push('--nofs');
	}

	if (opts.posterize) {
		args.push('--posterize', opts.posterize);
	}

	if (opts.quality) {
		args.push('--quality', opts.quality);
	}

	if (opts.speed) {
		args.push('--speed', opts.speed);
	}

	if (opts.verbose) {
		args.push('--verbose');
	}

	return execBuffer({
		input: buf,
		bin: pngquant,
		args
	}).catch(err => {
		err.message = err.stderr || err.message;
		throw err;
	});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.imagemin-pngquant.toString"></a>[function <span class="apidocSignatureSpan">imagemin-pngquant.</span>toString ()](#apidoc.element.imagemin-pngquant.toString)
- description and source-code
```javascript
toString = function () {
    return toString;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
