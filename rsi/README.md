# DataLite-RSI method contributions

Implementations live in `rsi/methods/<method-id>/`. Start from
[`../templates/method.json`](../templates/method.json) and keep the manifest ID
identical to the directory name.

At minimum, document:

- the state changed on each recursive iteration;
- feedback and acceptance signals;
- stopping criteria and resource budget;
- human intervention and external service requirements;
- safety checks, rollback behavior, and failure modes;
- supported DataLite-RSI tracks.

Prefer a model-independent core plus small model/provider adapters. Include a
deterministic smoke test that uses a mock or tiny local fixture rather than paid
APIs.
