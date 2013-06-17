# JavaScript code review checklist

## High arity

Is there confusion arising from high function arity?

> The number of arguments to this function makes the code hard to read, and it makes
  it easy to make mistakes when invoking the function. When you have functions like
  this that accept many arguments, it's a good idea to refactor them to accept a single
  argument, which is an object that has all of these arguments as properties.
>
> Some benefits of this approach:
> 
> * You can explicitly see what each argument means at the call site (because you're effectively using named parameters).
> * It's easy to omit optional arguments because you can just leave them off instead of having to explicitly pass `undefined`.

Does the diff add another positional argument to a function that already has several?

> This method has too many positional arguments. Adding another argument makes it worse.
  Let's make it better instead. This function should have a single argument, which is
  an object that has all of these arguments as properties.
>
> Some benefits of this approach:
> 
> * You can explicitly see what each argument means at the call site (because you're effectively using named parameters).
> * It's easy to omit optional arguments because you can just leave them off instead of having to explicitly pass `undefined`.
