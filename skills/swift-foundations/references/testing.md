# Swift Testing

## Preferred Framework

- Prefer Swift Testing over XCTest for new tests.
- Match an existing test target's framework only when consistency is more valuable than introducing a second framework.
- Use pointfreeco/swift-macro-testing for creating unit tests with macros.

## Testability

- Do not introduce protocols just for testing.
- Prefer testing through public behavior and small use cases.
- Use UseCaseMacro-generated dependencies when a view model or service needs injected behavior.
- Keep tests focused on meaningful behavior rather than implementation details.

## Style

- Name tests after the behavior being verified.
- Never write non-deterministic tests, such as those that rely on time, randomness, network, and process-global state.
- Never write a test that relies on something that can vary between machines or users, include time zones, regions, and languages.
