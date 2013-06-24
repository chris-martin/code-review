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

[How to Write Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html): OK to use phrases instead of complete sentences, in the interests of brevity. This holds especially in the initial summary and in @param tag descriptions. A method implements an operation, so it usually starts with a verb phrase."Gets the label of this button" is preferred to "This method gets the label of this button."

#### Javadoc needs a well-formed summary sentence

[How to Write Doc Comments for the Javadoc Tool](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html#descriptions): The first javadoc sentence should end with a period.

## Java 7 diamond

#### Use diamond syntax

In Java 7, you can use the [diamond syntax](http://docs.oracle.com/javase/7/docs/technotes/guides/language/type-inference-generic-instance-creation.html) to elide some generic type information that the compiler can infer. So this could be shortened to __________________.
