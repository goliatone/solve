# expand

CLI template expander

## Getting Started
Install the module with: `npm install expand -g`

```
 NODE_ENV=local NODE_USERNAME=peperone NODE_PASSWORD=shh expand examples/Dockerfile
```

```
expand examples/template.html -c examples/context.json
```

Use with `envset`:
```
envset production -- expand Dockerfile
```

## Documentation
_(Coming soon)_

## Examples
_(Coming soon)_

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_

## License
Copyright (c) 2015 goliatone  
Licensed under the MIT license.


#!/usr/bin/env node

var i = require('interpolate');

var options = { delimiter: '{{}}' };

var processLine = function(line){
	console.log(i(line, process.env, options));
};

process.stdin.resume();
process.stdin.setEncoding('utf8');
process.stdin.on('data', function(data){
	processLine(data);
});
