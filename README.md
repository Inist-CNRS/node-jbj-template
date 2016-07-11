# JBJ template module

JBJ template module: advanced use of variables within strings ([compute](#compute), [template](#template))

## Contributors

  * [Nicolas Thouvenin](https://github.com/touv)

## Installation

```bash
$ npm install jbj-template
```

## Usage

This JBJ module cannot be used alone. JBJ has to be installed.

```js
var JBJ = require('jbj');
JBJ.use(require('jbj-template'));
```

## Tests

Use [mocha](https://github.com/visionmedia/mocha) to run the tests.

```bash
$ npm install
$ npm test
```

## Actions

Once the module is declared as used for JBJ, you can use the following actions:

<a id="template"></a>
### template:  mustacheTemplate | [mustacheTemplate, mustacheTemplate, ...]

Build a string with [mustache](https://github.com/janl/mustache.js) template
and *input*

```javascript
    var stylesheet = {
        "set" : {
            "a" : {
                "b" : "hello"
            },
            "c" : "world"
        },
        "template": "I say {{a.b}} to the {{c}}"
    };
    // output : I say hello to the world
```

<a id="templateUrl"></a>
### templateUrl: url

Build a string with [mustache](https://github.com/janl/mustache.js) template
taken from an external file and *input*.

The template file is accessed *via* an URL (the protocol has to be defined, see
[register](https://github.com/Inist-CNRS/node-jbj#register) and
[source](https://github.com/Inist-CNRS/node-jbj#source)).

In the example below, the content of `file://./test/template.mustache` is
`X{{a.b.c}}X{{a.d}}X{{a.e}}X{{f}}`.

```json
{
      "input": {
          "a" : {
              "b" : {
                  "c" : "1"
              },
              "d" : "2",
              "e" : "4"
          },
          "f": "8"
      },
      "stylesheet": {
          "templateURL": "file://./test/template.mustache"
      },
      "expected":  "X1X2X4X8\n"
  }
```


## Examples

See unit tests : https://github.com/Inist-CNRS/node-jbj-template/tree/master/test


## Try it

http://Inist-CNRS.github.io/node-jbj/


## License

[MIT](https://github.com/Inist-CNRS/node-jbj-template/blob/master/LICENSE)
