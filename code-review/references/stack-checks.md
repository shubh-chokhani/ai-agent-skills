# Conditional stack checks

Apply only checks supported by the changed code and detected dependencies.

## Java and Spring

- Check transactions, lazy loading, connection ownership, and query growth across loops. Verify assumptions against the actual database and ORM.
- Check Spring proxy boundaries: self-invocation can bypass proxy-based transactional or asynchronous behavior. Confirm the application's proxy configuration before flagging it.
- Trace validation and authorization through controllers, service methods, and error mapping. Avoid exposing implementation details in client errors.
- For message consumers, inspect acknowledgment ordering, replay behavior, deduplication, and poison-message handling.
- Check executor bounds, request context propagation, cancellation, and timeout interactions when concurrency changes.
- Verify serialization and mapping contracts, including null handling and changes to generated mappers. Use existing test conventions.

## JavaScript, TypeScript, and React

- Trace stale closures, effect dependencies, cleanup, and response ordering during rapid navigation or input changes.
- Check hooks remain unconditional and state updates preserve identity where required. Evaluate rerenders only when there is a demonstrated cost.
- Inspect loading, empty, failure, and retry states; check keyboard interaction and accessible semantics for changed UI.
- Trace untrusted values into HTML, URLs, storage, and API calls. Static types do not validate runtime input.
- Check API and exported component contracts, module compatibility, and server/client execution boundaries where applicable.
- Prefer tests of user-visible behavior. Mock external boundaries without replacing the logic being checked.
