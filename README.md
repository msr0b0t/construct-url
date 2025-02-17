# @iamnapo/construct-url

> Small utility function to construct URLs, without caring about slashes or encoding

[![build](https://img.shields.io/github/workflow/status/iamnapo/construct-url/ci?style=for-the-badge&logo=github&label=)](https://github.com/iamnapo/construct-url/actions) [![npm](https://img.shields.io/npm/v/@iamnapo/construct-url.svg?style=for-the-badge&logo=npm&label=)](https://www.npmjs.com/package/@iamnapo/construct-url) [![size](https://img.shields.io/bundlephobia/min/@iamnapo/construct-url.svg?style=for-the-badge&label=size)](https://bundlephobia.com/result?p=@iamnapo/construct-url)

## Install

```sh
$ npm i @iamnapo/construct-url
```

## Usage

```js
import constructUrl from "@iamnapo/construct-url";

constructUrl("https://example.com", "/foo"); // => "https://example.com/foo"
constructUrl("https://example.com/foo", "/bar"); // => "https://example.com/foo/bar"
constructUrl("https://example.com", "/foo", { bar: true }); // => "https://example.com/foo?bar=true"
constructUrl("https://example.com", "", { bar: true }); // => "https://example.com/?bar=true"
constructUrl("https://example.com", "/foo", { "//bar//": true }); // => "https://example.com/foo?%2F%2Fbar%2F%2F=true"
```

## API

### constructUrl(base, path?, query?)

Get a full URL, including encoded query parameters.

#### base

Type: `string | URL`

Base URL.

#### path

Type: `string`\
Default: `""`

Path relative to `base`.

#### query

Type: `string | [[string, any]] | { [key: string]: any } | URLSearchParams`\
Default: `""`

Query parameters to include in the resuliting URL.
