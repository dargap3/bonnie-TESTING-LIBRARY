## React testing library is not only a library, it's also a philosophy of how to test

## Best practices:

- Test your software the way users actually use it.
- Remove internal implementation.
- Find elements by accessibility markers, not tests IDs.


React testing library

Provides simulated DOM for tests
Provides ways to manipulate and examine simulated DOM (click buttons and see how things look after we click the button)
Renders components into simulated DOM
Makes simulated DOM availale for assertions and interactions
Needs a test runner

Creates virtual DOM for testing and utilities for interacting with DOM
Allos testing without a browser

jest/vitest

Test runner: finds tests, runs tests, determines whether tests pass or fail, makes assetions

 

In a big picture there is no differences between jest and vitest, only the setup  and some minor differences when we use advance syntax.

Global test method hast two arguments:

-string description
-test function

Test fails if error is thrown when running function
 -assertions throw errors when expectaction fails
No error _> test pass

Empty test passes.



render
create simulated DOM for argument component
access simulated DOM via screen global

Assertions:

they all start with expect method (global method from jest/vitest)
expect argument is the subject of the assertion 
matcher comes from jest-DOM
matcher argument --> refines matcher


TDD

Test driven development

Write tests before writing code - then crite code according to "spec" set by tests

it's often called "red-green" testing --> tests fail before code is written and after code is written the tests pass.

Why TDD?

Makes a huge difference in how it feels to write tests.
Part of the coding process, not a "chore" to do at the end
More efficient
Re-run tests "for free" after changes (free regression testing)




jest-DOM
imported before each test (by test setup) makes matchers available
dom-based matchers

Types of tests:

Unit tests
Tests One unit of code in isolation

Integration tests
How multiple units work together

Functional tests
tests a particular function of software (enter data in a form and click submit)

Acceptance / end to end E2E tests
use actual browser and server (cypress, selenium)

Unit testing functions
whenever we have functions in our react app, we should unit test if:
  the logic is difficult to test via functional tests
  too many edge cases
  determine what caused functional tests to fail

  Issue with functional tests:
    high-level makes them resistant to refactors
    high-level makes them difficult to diagnose


https://github.com/bonnie/udemy-TESTING-LIBRARY
https://vitest.dev/guide/migration#migrating-from-jest
https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#roles
https://testing-library.com/docs/queries/about/#priority


