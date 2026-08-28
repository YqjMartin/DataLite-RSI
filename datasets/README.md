# Dataset registry

This directory contains metadata and immutable references, not large dataset
files. Canonical Lite-RSI data is hosted at
[`lhpku20010120/Lite-RSI`](https://huggingface.co/datasets/lhpku20010120/Lite-RSI).

To register a dataset:

1. publish the data and Dataset Card on Hugging Face;
2. obtain the exact Hugging Face commit SHA;
3. create `datasets/<dataset-id>/dataset.json` from
   [`../templates/dataset.json`](../templates/dataset.json);
4. add a README covering provenance, license, privacy, safety, and limitations;
5. run the repository validator.

Benchmarks refer to the registry `id`, while result manifests also record the
exact dataset revision used in that run.

