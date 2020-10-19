# Fakefile

A Universal Makefile for JavaScript that proxies to your npm scripts. 

## How

After installing, you can type `mak<TAB><TAB>` for [autocompletion](https://davidalger.com/development/bash-completion-on-os-x-with-brew/). Fakefile then quickly enumerates any npm scripts in your `package.json` and presents these. It does this at runtime, so it won't need any maintenance as your project changes its npm scripts.

## Why 

This gets us the best of both worlds. Codify your tasks in a system (npm scripts) that won't be obsolete within the year, that's straightforward to people on Windows (they can ignore the Makefile and use `npm run`), and unix folks alike. Profit from instant autocomplete. In any repo I maintain, no matter the language, `make <something>` gets me what I want without thinking twice.

I wrote a [blog post](https://kvz.io/blog/2016/02/18/a-universal-makefile-for-javascript/) that goes into more detail why this makes for a great JavaScript task running environment.

## Use 

Run e.g. `make test` and the command is passed onto `npm run test` that should do the lower-level plumbing.

Makefiles can't handle `:` characters well so it will offer `npm run build:production` to you as `make build-production`.

## Install

You could save Fakefile's [`Makefile`](https://raw.githubusercontent.com/kvz/fakefile/master/Makefile) into your project root, and that's that.

Alternatively, you can use the npm installer:

```bash
npm install fakefile --save-dev --save-exact 
```

This will save a Makefile into your project root. 

If the installer detects a Makefile it does not recognize by its sha1 hash, it will warn you instead of overwriting it. This gives you a chance to port any existing Makefile logic to npm scripts, after which you can safely remove your original Makefile and rerun the installation, this time successfully installing Fakefile. The installer is happy to overwrite known sha1s, so that we can upgrade should the need arise.

## Authors

- Kevin van Zonneveld (<https://kvz.io>)

## License

Copyright (c) 2016 Kevin van Zonneveld, [https://kvz.io](https://kvz.io)  
Licensed under MIT: [https://kvz.io/licenses/LICENSE-MIT](https://kvz.io/licenses/LICENSE-MIT)
