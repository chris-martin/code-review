# JavaScript code review checklist

## Equality operators

#### Use `===` to compare with `null` or `undefined`

[Do not use `==` or `!=`](http://www.jslint.com/lint.html):

> The == and != operators do type coercion before comparing. This is bad because it causes `' \t\r\n' == 0` to be `true`. This can mask type errors. It is best to not use `==` and `!=` at all and to always use the more reliable `===` and `!==` operators instead.

> If you only care that a value is truthy or falsy, then use the short form. Instead of `(foo != 0)` just say `(foo)` and instead of `(foo == 0)` say `(!foo)`.

#### Use `===` to compare strings

...

## High arity

#### Keep arity low

The number of arguments to this function makes the code hard to read, and it makes it easy to make mistakes when invoking the function. When you have functions like this that accept many arguments, it's a good idea to refactor them to accept a single argument, which is an object that has all of these arguments as properties.

#### Don't increase arity

This method has too many positional arguments. Adding another argument makes it worse. Let's make it better instead. This function should have a single argument, which is an object that has all of these arguments as properties.

#### Additional comments on named arguments

Some benefits of this approach:

* You can explicitly see what each argument means at the call site (because you're effectively using named parameters).
* It's easy to omit optional arguments because you can just leave them off instead of having to explicitly pass `undefined`.

There is no particular convention for what to name the one parameter, but it can just be something generic like `params`, `options`, or `config`.

Make sure the documentation includes a list of all of the properties that the config object may have. There is no particular convention on how to format this documentation, but include all of the same information you would if you were documenting function arguments.

For optional parameters, use a value of `undefined` rather than `null`, so the caller can just entirely omit any parameters it does not care to specify.
