# Code review checklist (for all languages)

## Comments

 [A good philosophy](http://agileinaflash.blogspot.com/2009/04/rules-for-commenting.html):

* Comments provide information that is not expressible in code.
* Comments are to be deleted when they are obviated.
* We should always strive to obviate comments.

## Boolean parameters

#### One boolean parameter

Boolean method parameters are generally a bad idea, because it's hard to figure out what's going on when you're looking at the call site.

#### Multiple boolean parameters

Boolean method parameters are generally a bad idea, because it's hard to figure out what's going on when you're looking at the call site. *Multiple* boolean parameters are an especially bad idea, because it's easy to mix them up. If a call is `foo(true, false)` when it should be `foo(false, true)`, no one's going to notice the mistake.
