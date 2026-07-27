## Tasks
- [ ] Add a note that is can be renamed on export as check or whatever
- [x] Remove predicate form for is.
- [x] Rename runner parameter to current-test-runner
- [x] Add set test runner API
(define (set-current-test-runner! obj)
  (current-test-runner obj))
- [x] Mention SRFI-229 and SRFI-259 for tagged procedures.
- [x] Add description to is (is (form args) "description")
- [ ] Add note that test or assertion can be re-executed multiple times.
- [x] Remove assoc-ref
- [x] Add clojure like syntax for test ctx (test "descr" () ...)
- [ ] Add info on how to set suite/description in define-suite

## Questions
- [.] Add description to define-suite (name "optional description").
      Can be done with metadata if needed.
- [ ] Make is flexible enough to implement expect https://www.futurile.net/2020/07/14/clojure-testing-with-clojure-test-and-expectations/

- [ ] Add test-loader and define-suite to normative API?
- [x] Description in paranthesis together with context is confusing
- [-] Wrap metadata in parenthesis
- [ ] Make it clear how context is constructed and modified (immutable
      alist with sideeffectful values).
- [ ] Add runner/run-tests message or define reccomendation for running
- [ ] Establish baseline for ctx value of the test
- [ ] Add `test/id`, `suite/id` recommendation to SRFI
- [ ] 5. A definition of "fixture value" would be helpful.  (Pardon my
      ignorance of testing jargon.)
- [ ] Do we need to discover all tests or only exported?
- [x] Make context optional for test. An empty context list ignores context.
- [x] is accept description as a second argument
- [x] Rename body-thunk to body-procedure?
- [x] define-suite uses parenthesis around the suite name
- [-] Change description format to `("description" (slow? . #t) (hek? . #t))
- [x] Rename assert to assertion?

- [x] What if the assertion would just throw an exception? (simpler,
      but less flexible? How it will communicate the result to test?)
      We will use the control on assertion execution
      environment. Won't be able to treat error as ok outcome and run
      further assertions.

- [-] Make suite-thunk return an alist and (run-suite-thunk ...) run
      it? For portable implementations without procedure tags.

- [ ] Make destructuring great again. (Implement it on suitbl/SRFI or separate?)
- [ ] is macro as a syntax parameter set by context?
- [-] with-ctx
- [-] with-metadata macro
- [-] (suite-loader-constructor metadata) -> (suite-loader ctx) (2 pass before load)

- [x] Where to put metadata? Before or after `(ctx)`.  (After `(ctx)`)
- [-] define-suite accept docstring (set via metadata if necessary)
- [x] Call suite-loader with metadata
- [-] Rename define-suite to define-suite-loader/define-suitel
- [x] Do we need to wrap define-suite in parenthesis? (yes, same same as define-stream)
- [ ] Split test/name and test/description, suite/name and
      suite/description. Check out
      https://clojuredocs.org/clojure.test/testing
