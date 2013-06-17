# JavaScript code review checklist

## High arity

Does the diff add another positional argument to a function that already has several?

> This method has too many positional arguments. Adding another argument makes it worse.
  Let's make it better instead. This function should have a single argument, which is
  an object that has all of these argument as properties.
