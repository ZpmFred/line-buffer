![Build Status](https://travis-ci.org/xpepermint/line-buffer.svg?branch=master)&nbsp;[![NPM Version](https://badge.fury.io/js/line-buffer.svg)](https://badge.fury.io/js/line-buffer)&nbsp;[![Dependency Status](https://gemnasium.com/xpepermint/line-buffer.svg)](https://gemnasium.com/xpepermint/line-buffer)

# line-buffer

> For reading stream's data as lines.

This is an open source [npm](http://npmjs.com) package from [Node.js](http://nodejs.org). The source code is available on [GitHub](https://github.com/xpepermint/line-buffer) where you can also find our [issue tracker](https://github.com/xpepermint/line-buffer/issues).

## Install

```
$ npm install --save line-buffer
```

## Example

```js
import {LineBuffer} from 'line-buffer';

let buffer = new LineBuffer();
buffer.feed('abc\ndef\r\nghi'); //-> ['abc', 'def', 'ghi']
buffer.feed('123\r'); //-> []
buffer.feed('\n456'); //-> ['123']
buffer.feed('\n'); //-> ['456']
```

## API

**LineBuffer()**

> A core buffer class.

**linebuffer.feed(data)**:Array

> A method for feeding the buffer with data.

| Option | Type | Required | Default | Description
|--------|------|----------|---------|------------
| data | String|Buffer | No | - | A chunk of data to fill the buffer.

**linebuffer.drain()**

> A method for clearing the buffer.

**Event: linebuffer.on('line', (line) => {})**

> Emitted when a new line of data is available.

| Argument | Type | Description
|--------|------|----------
| line | Buffer | A line of data.

**Event: linebuffer.on('drain', () => {})**

> Emitted when the buffer is cleared.

## License (MIT)

```
Copyright (c) 2016 Kristijan Sedlak <xpepermint@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
