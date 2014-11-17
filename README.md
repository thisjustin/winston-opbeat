winston-opbeat
==============

A Winston transport for sending logs to [Opbeat](http://opbeat.com)

## Installation

### Installing npm (node package manager)

``` sh
  $ curl http://npmjs.org/install.sh | sh
```

### Installing winston-opbeat

``` sh
  $ npm install winston
  $ npm install winston-opbeat
```

## Usage
``` js
  var winston = require('winston');

  //
  // Requiring `winston-opbeat` will expose
  // `winston.transports.Opbeat`
  //
  require('winston-opbeat').Opbeat;

  winston.add(winston.transports.Opbeat, options);
```


### Options  
* __opbeat:__ instance of opbeat
* __level:__ level of logs you want to send to Opbeat
* __silent:__ turn off sending to Opbeat (useful for dev)


### Logging  
It's best if you send an instance of `Error` to Opbeat for tracking. Send the `Error` instance in the `meta` field of your Winston logger and it will be parsed and passed to Opbeat (along with any other info you include in `meta`).

Example logging:
```javascript
// replace logger.error with however you call Winston
logger.error('Some message', {error: new Error('Pass your error or init a new one here'), info: 'additional info to pass to opbeat'});
```

## License
The MIT License (MIT)
(c) 2014 Justin McCammon

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.