# Testing code review checklist

## One assertion per test

As a general rule, each unit test should only have a single assertion. With multiple asserts in a single test, the test can only fail on the first error, so the test output which isn't as helpful if there is more than one failure.
