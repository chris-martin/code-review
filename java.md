# Java code review checklist

## Nullable

Are there nullable parameters or return values that are missing the `@Nullable` annotation?

> Please add the `javax.annotation.Nullable` annotation to this method to indicate that
  the return type may be `null`.

> Please add the `javax.annotation.Nullable` annotation to this parameter to indicate
  that `null` values are accepted.

## Related methods

Are there two similar methods, but the connection between them is undocumented?

> Please add a note to this method that mentions the other, and vice versa,
  (with a mention in both places of how they differ), to enhance the
  discoverability of this API. You can link them with `@see #methodName`.

## Javadoc summary sentence

Does a method javadoc start with "This method ..."?

> [How to Write Doc Comments for the Javadoc Tool](http://goo.gl/lKYoc):
  OK to use phrases instead of complete sentences, in the interests of brevity.
  This holds especially in the initial summary and in @param tag descriptions.
  A method implements an operation, so it usually starts with a verb phrase.
  "Gets the label of this button" is preferred to
  "This method gets the label of this button."

