[https://github.com/bonnie/udemy-TESTING-LIBRARY](https://github.com/bonnie/udemy-TESTING-LIBRARY)  *base repo*

# TDD - Test driven development

- Write tests before writing code - then crite code according to "spec" set by tests.
- It's often called "red-green" testing --> tests fail before code is written and after code is written the tests pass.

## Why TDD?

   - Makes a huge difference in how it feels to write tests.
   - Part of the coding process, not a "chore" to do at the end.
   - More efficient.
   - Re-run tests "for free" after changes (free regression testing)

   ### Types of tests:

   #### Unit tests
   Tests One unit of code in isolation

   #### Integration tests
   How multiple units work together

   #### Functional tests
   Tests a particular function of software (enter data in a form and click submit)

   #### Acceptance / end to end E2E tests
   Use actual browser and server (cypress, selenium)

   ## Unit testing functions
   **Whenever we have functions in our react app, we should unit test if:**
   -  The logic is difficult to test via functional tests
   -  Too many edge cases.
   -  Determine what caused functional tests to fail.
 
   ### Issue with functional tests:
   - High-level makes them resistant to refactors.
   - High-level makes them difficult to diagnose.
  
## React testing library

  - Provides simulated DOM for tests.
  - Provides ways to manipulate and examine simulated DOM (click buttons and see how things look after we click the button)
  - Renders components into simulated DOM.
  - Makes simulated DOM availale for assertions and interactions.
  - Needs a test runner.
  - Creates virtual DOM for testing and utilities for interacting with DOM.
  - Allow us testing without a browser.

  **React testing library is not only a library, it's also a philosophy of how to test**

  **Includes best practices:**
  - Test your software the way users actually use it.
  - Remove internal implementation.
  - Find elements by accessibility markers, not tests IDs.

  [https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#roles](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#roles)  *web accessibility roles*  
  [https://testing-library.com/docs/queries/about/#priority](https://testing-library.com/docs/queries/about/#priority)  *queries priority*  
  [https://testing-library.com/docs/react-testing-library/cheatsheet/](https://testing-library.com/docs/react-testing-library/cheatsheet/)  *react testing library cheatsheet*  

## jest/vitest

  - Test runner: finds tests, runs tests, determines whether tests pass or fail, makes assetions.
  - In a big picture there is no differences between jest and vitest, only the setup  and some minor differences when we use advance syntax.

  [https://vitest.dev/guide/migration#migrating-from-jest](https://vitest.dev/guide/migration#migrating-from-jest)  *guide to migrate from jest to vitest*

##  jest-DOM

  - Imported before each test (by test setup) makes matchers available.
  - Dom-based matchers.

  [https://github.com/testing-library/jest-dom](https://github.com/testing-library/jest-dom)  *jest dom documentation*  

## Global test method (jest/vitest):

  `test('', () => {});`

  - Global test method has two arguments:
    1. string description
    2. test function

  - Test fails if error is thrown when running function.
  - Assertions throw errors when expectaction fails.
  - No error ---> test pass.
  - Empty test passes.

## Render (RTL):
  - create simulated DOM for argument component.
  - access simulated DOM via screen global.

## Assertions:

  - They all start with expect method (global method from jest/vitest).
  - Expect argument is the subject of the assertion.
  - Matcher comes from jest-DOM.
  - Matcher argument --> refines matcher

    `expect(data).toEqual({one: 1, two: 2});`

## Fire events vs User events

  - In general fire events is ok, but user event is better.
  - It simulates events in a more complete and realistic way than fire event.
  - Fire event dispatches dom events, is a way to simulate computer events.
  - User event simulate full and complete user interactions.

## User Event
  - Whenever we use user event, we need to start a session with the setup method.
  - The user event apis always return a promise.
  - We need to use await.
    
  [https://github.com/testing-library/user-event](https://github.com/testing-library/user-event)  *user event documentation*  
  [https://github.com/testing-library/user-event](https://github.com/testing-library/user-event)  *user event documentation*  

## screen Query Methods
**command[All]ByQueryType**

  ### comand:
   - get: expect element to be in DOM.
   - query: expect element not to be in DOM.
   - find: expect element to appear async.

  ### [All]
   - (exclude) expect only one match.
   - (include) expect more than one match.

  ### QueryType:
   - Role (most preferred)
   - AltText (images)
   - Text (display elements)
   - Form elements
     - PlaceholderText
     - LabelText
     - DisplayValue

  [https://testing-library.com/docs/queries/about/](https://testing-library.com/docs/queries/about/)  *RTL queries docs*  

  ## Mock Service Worker
   - Purpuse:
     - intercept network calls.
     - return specified responses.
   - Prevents network calls during tests.
   - Set up test conditions using server response.

   ### set up
    - Install it.
    - Create handlers. Handlers are functions that will determine what is returned for any particular URL and route.
    - Create test server.
    - Make sure test server listens during all tests.
     - Reset after eact test.

   ### Mock service worker handler
     - Handler type: http or graphql
     - Http method to mock: get, post, etc.
     - Full URL to mock.

  [https://mswjs.io/](https://mswjs.io/)  *MSW documentation*   
  [https://mswjs.io/docs/basics/mocking-responses](https://mswjs.io/docs/basics/mocking-responses)  *MSW mocking responses*   
  [https://mswjs.io/docs/integrations/node](https://mswjs.io/docs/integrations/node)  *Node integration*  
  [https://mswjs.io/docs/network-behavior/rest#response-resolver](https://mswjs.io/docs/network-behavior/rest#response-resolver)  *MSW response resolver*  
  [https://mswjs.io/docs/runbook/](https://mswjs.io/docs/runbook/)  *MSW run book*  
  
