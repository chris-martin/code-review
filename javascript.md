# JavaScript code review checklist

## `==`

Is `==` or `!=` used to compare with `null` or `undefined`?

> Don't use `==` or `!=` to compare with `null` or `undefined`.
  It's misleading because `null == undefined` but `null !== undefined`.
  There are very few reasons to use `==` and `!=` in JavaScript.
  If you need to check whether something is `null`, use `===` or `!==`.

```
if (result && Integer.parseInt(result.getGroup(1)) >= 8) {
```

## High arity

Is there confusion arising from high function arity?

> The number of arguments to this function makes the code hard to read, and it makes
  it easy to make mistakes when invoking the function. When you have functions like
  this that accept many arguments, it's a good idea to refactor them to accept a single
  argument, which is an object that has all of these arguments as properties.

Does the diff add another positional argument to a function that already has several?

> This method has too many positional arguments. Adding another argument makes it worse.
  Let's make it better instead. This function should have a single argument, which is
  an object that has all of these arguments as properties.

#### Additional commits on named arguments

> Some benefits of this approach:
> 
> * You can explicitly see what each argument means at the call site (because you're
>   effectively using named parameters).
> * It's easy to omit optional arguments because you can just leave them off instead
>   of having to explicitly pass `undefined`.
>
> There is no particular convention for what to name the one parameter, but it can just
> be something generic like `params`, `options`, or `config`.
>
> Make sure the documentation includes a list of all of the properties that the config
> object may have. There is no particular convention on how to format this documentation,
> but include all of the same information you would if you were documenting function
> arguments.
>
> For optional parameters, use a value of `undefined` rather than `null`, so the caller
> can just entirely omit any parameters it does not care to specify.
