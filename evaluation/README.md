# DataLite-RSI evaluation contract

DataLite-RSI evaluators should expose a deterministic, scriptable entry point. A
track-specific implementation may add fields, but the evaluation record should
always identify:

- benchmark ID and version;
- dataset revision;
- model and method IDs;
- baseline and post-RSI metrics;
- iteration and compute budgets;
- seeds and generation settings;
- code commit and container digest;
- output artifact locations.

Evaluators should separate model inference from metric computation whenever
practical. This allows independent verification from saved predictions without
requiring access to the original model or API.

The initial cross-track evaluator API will be added with the first benchmark.
