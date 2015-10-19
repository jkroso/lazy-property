lazy-property
=============
Adds a lazily initialized property to an object.

## Example

```javascript
var addLazyProperty = require("lazy-property")

var obj = {}

addLazyProperty(obj, "foo", function() {
  console.log("initialized!")
  return "bar"
})

//Access the property
console.log(obj.foo)
console.log(obj.foo)

//Prints out:
//
//    initialized!
//    bar
//    bar
//
```

## Install

    npm install lazy-property

## API

### `require("lazy-property")(obj, name, init[, enumerable])`
Adds a lazily initialized property to the object.

* `obj` is the object to add the property to
* `name` is the name of the property
* `init` is a function that computes the value of the property
* `enumerable` if the property is enumerable (default `false`)

### `@lazy`
ES7 decorators enable a nicer syntax for defining lazy properties

```js
const lazy = require("lazy-property/decorator")

class Example {
  @lazy foo(){ return "computed value of foo" }
  @lazy("enumerable") bar(){ return "bar shows up in for in loops" }
}
```

## Credits
(c) 2013 Mikola Lysenko. MIT License
