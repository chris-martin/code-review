# Java code review checklist

## Nullable

#### Nullable *return values* need a `@Nullable` annotation

Please add the `javax.annotation.Nullable` annotation to this method to indicate that the return value may be `null`.

#### Nullable *parameters* need a `@Nullable` annotation

Please add the `javax.annotation.Nullable` annotation to this parameter to indicate that `null` values are accepted.

## Related methods

#### Document the relation between similar methods

Please add a note to this method that mentions the other, and vice versa, (with a mention in both places of how they differ), to enhance the discoverability of this API. You can link them with `@see #methodName`.

## Javadoc summary sentence

#### Method javadoc starting with "This method ..."

It's okay to use phrases instead of complete sentences, in the interests of brevity. This holds especially in the initial summary and in @param tag descriptions. A method implements an operation, so it usually starts with a verb phrase."Gets the label of this button" is preferred to "This method gets the label of this button." ([How to Write Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html#descriptions))

#### Javadoc needs a well-formed summary sentence

The first javadoc sentence should end with a period. ([How to Write Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html#descriptions))

## Java 7 diamond

#### Use diamond syntax

In Java 7, you can use the [diamond syntax](http://docs.oracle.com/javase/7/docs/technotes/guides/language/type-inference-generic-instance-creation.html) to elide some generic type information that the compiler can infer. So this could be shortened to __________________.

## Introducing a type to reduce arity

The number of arguments to this function makes the code hard to read, and it makes it easy to make mistakes when invoking the function. When you have functions like this that accept many arguments, it's a good idea to introduce a new type that has a field for each argument.

The class can be very minimal:

```
public final class _____ {
    public ______ _____;
    public ______ _____;
}
```

Some benefits of this approach:

* You can explicitly see what each argument means at the call site (because you're effectively using named parameters).
* The class can specify default values for its fields, so callers can simply omit values they don't care to specify. You won't have to pass `null` values or use overloaded methods that accept different subsets of the parameters.
* If these parameters have to be passed along through a series of method calls, you'll only have to pass a single parameter.

## Replacing `{0}` in strings

Write `java.text.MessageFormat.format(a, b)` instead of `a.replace("{0}", b)`.

## `<code>` in javadoc

The `{@code x}` syntax [introduced in Java 5](https://blogs.oracle.com/darcy/entry/javadoc_tip_code_and_literal) is preferred to `<code>x</code>`.

