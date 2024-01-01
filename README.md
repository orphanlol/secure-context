# secure-context
idk why this is such a hard concept for some people.
use this to help your self. please, its too easy.

```
function secureContext(methods) {
    const securedMethods = {};
    methods.forEach(method => {
        securedMethods[method.name] = method;
    });
    return securedMethods;
}

let context = secureContext([
    console.log,
    debug,
    fetch
]);

// remove functions
console.log = () => {}
debug = () => {}
fetch = () => {}

// doesnt work because overriden
console.log('Hello World!')

// can still use
context.log('Hello World!')
```
