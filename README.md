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

<a id="compute"></a>
### compute: expression

Compute an expression with all variables of the *input*. Use the [filtrex](https://github.com/joewalnes/filtrex#expressions) syntax.
Note : `this` variable contains *input*
```javascript
    var stylesheet = {
        "set" : {
            "a" : 20,
            "b" : 3,
            "c" : 5,
            "d" : 8
        },
        "$x" : {
            "compute#1": "a / b",
            "compute#2": "round(this)",
            "cast": "number"
        },
        "$y" : {
            "path": "b",
            "cast": "number"
        },
        "$z" : {
            "compute": "x + y",
        }
    };
    // output : 10
```

## Examples

See unit tests : https://github.com/Inist-CNRS/node-jbj-template/tree/master/test


## Try it

http://Inist-CNRS.github.io/node-jbj/


## License

[MIT](https://github.com/Inist-CNRS/node-jbj-template/blob/master/LICENSE)
