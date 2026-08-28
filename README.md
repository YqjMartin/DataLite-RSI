# Lite-RSI

**Less Is More for Recursive Self-Improvement**

Lite-RSI is an open research project for studying recursive self-improvement
(RSI) under explicit intervention and compute budgets. The project is designed
to support comparable experiments across large language models, multimodal
models, and generative models.

> Project status: early-stage infrastructure. Benchmark tasks, reference
> evaluators, and the first verified results are being prepared.

## Tracks

| Track | Typical systems | Example evaluation targets |
| --- | --- | --- |
| LLM | chat, reasoning, coding, and agent models | accuracy, pass rate, cost, and improvement per iteration |
| Multimodal | vision-language and audio-language models | perception, reasoning, grounding, and multimodal generation |
| Generative | image, video, audio, and other generators | quality, alignment, diversity, and efficiency |

## Contribute

There are four independent contribution routes. You do not need to implement
the complete Lite-RSI stack to contribute one component.

| Contribution | What belongs in GitHub | Start here |
| --- | --- | --- |
| Benchmark | task manifest, evaluator, tests, and documentation | [Benchmark guide](benchmarks/README.md) |
| Dataset | metadata, provenance, license, and a pinned Hugging Face revision | [Dataset guide](datasets/README.md) |
| Result | result manifest, settings, reproducibility metadata, and small summaries | [Result guide](results/README.md) |
| RSI method | method manifest, source code, configuration, tests, and documentation | [RSI method guide](rsi/README.md) |

Read [CONTRIBUTING.md](CONTRIBUTING.md) for the complete pull-request process,
or read the [Chinese contribution guide](docs/CONTRIBUTING_zh.md).

## Storage policy

- **GitHub:** source code, manifests, Dockerfiles, tests, documentation, and the
  project website.
- **Hugging Face:** benchmark data and other large ML artifacts. The canonical
  dataset repository is
  [`lhpku20010120/Lite-RSI`](https://huggingface.co/datasets/lhpku20010120/Lite-RSI).
- **GHCR:** built Docker/OCI images, for example
  `ghcr.io/haolpku/lite-rsi-eval:<version>`.

Do not commit model weights, dataset archives, Docker image tarballs, generated
media, API keys, or other large binary artifacts to this repository.

## Repository layout

```text
benchmarks/          Benchmark definitions and evaluator implementations
datasets/            Dataset metadata and pinned Hugging Face references
evaluation/          Shared evaluation interfaces and metric conventions
results/             Result submissions and the generated leaderboard
rsi/                 RSI method implementations
docker/              Reproducible evaluation environments
schemas/             Machine-readable contribution schemas
templates/           Copyable manifest templates
scripts/             Repository validation utilities
.github/              Issue forms, pull-request template, and CI workflows
```

## Validate a contribution

The repository validator uses only the Python standard library:

```bash
python scripts/validate_contributions.py .
python -m unittest discover -s tests -v
```

The same validation can run without installing Python dependencies locally:

```bash
docker build -f docker/validator/Dockerfile -t lite-rsi-validator .
docker run --rm -v "$PWD:/workspace:ro" lite-rsi-validator /workspace
```

## Reproducibility contract

A verifiable result must identify all of the following:

1. benchmark ID and version;
2. model and RSI method;
3. complete evaluation settings and random seeds;
4. Git commit for the evaluation and method code;
5. immutable Hugging Face dataset revision;
6. versioned container image, preferably pinned by `sha256` digest;
7. command used to reproduce the run.

Results are submitted as **unverified**. Maintainers verify them before adding
them to the public leaderboard.

## Citation

Paper and citation information will be added with the first Lite-RSI release.

