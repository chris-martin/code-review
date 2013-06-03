# Java code review checklist

## Nullable

Are there nullable **return values** that are missing the `@Nullable` annotation?

> Please add the `javax.annotation.Nullable` annotation to this method to indicate that
  the return value may be `null`.

Are there nullable **parameters** or return values that are missing the `@Nullable` annotation?

> Please add the `javax.annotation.Nullable` annotation to this parameter to indicate
  that `null` values are accepted.

## Related methods

Are there two similar methods, but the connection between them is undocumented?

> Please add a note to this method that mentions the other, and vice versa,
  (with a mention in both places of how they differ), to enhance the
  discoverability of this API. You can link them with `@see #methodName`.

## Javadoc summary sentence

Does a method javadoc start with "This method ..."?

> [How to Write Doc Comments for the Javadoc Tool]
  (http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html):
  OK to use phrases instead of complete sentences, in the interests of brevity.
  This holds especially in the initial summary and in @param tag descriptions.
  A method implements an operation, so it usually starts with a verb phrase.
  "Gets the label of this button" is preferred to
  "This method gets the label of this button."

## Java 7 diamond

Does code at the Java 7 language level include redundant type information that could be
elided using the diamond syntax?

> In Java 7, you can use the [diamond syntax]
  (http://docs.oracle.com/javase/7/docs/technotes/guides/language/type-inference-generic-instance-creation.html)
  to elide some generic type information that the compiler can infer.
  So this could be shortened to __________________
