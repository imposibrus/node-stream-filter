# stream-filter

Filter data using a [through stream](https://github.com/rvagg/through2).

[![build status](https://img.shields.io/travis/parshap/node-stream-filter.svg)](https://travis-ci.org/parshap/node-stream-filter)

# Example

```js
var filter = require("stream-filter");

process.stdin.pipe(filter(function(data) {
	return data.length > 2;
})).pipe(process.stdout);
```

## Using an Async Test

```js
var filter = require("stream-filter");

process.stdin.pipe(filter.async(function(data, callback) {
	doAsyncThing(data, function(err, size) {
		callback(err, size > 2);
	});
})).pipe(process.stdout);
```


# Installation

```
npm install stream-filter
```
