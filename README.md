mcp3424
=======

node.js module to read from MCP3424 4Channel Delta Sigma ADC

# Install

````bash
$ npm install mcp3424
````

# Example

```javascript
var MCP3424 = require('mcp3424');

var address = 0x68;
var gain = 0; //{0,1,2,3} represents {x1,x2,x4,x8}
var resolution = 3; //{0,1,2,3} and represents {12,14,16,18} bits

var mcp = new MCP3424(address, gain, resolution, '/dev/i2c-1');

setTimeout(function(){
  console.log(mcp.getMv(0)); //for channel 0
  console.log(mcp.getMv(3)); //for channel 3
}, 2000); //first conversion needs a bit time...(smaller resolution -> faster)
````

# Known issues
Maybe issues with negative values.
