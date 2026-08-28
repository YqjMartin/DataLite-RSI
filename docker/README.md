# Docker environments

Dockerfiles are version-controlled here; built images are published to GitHub
Container Registry (GHCR). Data and model weights are mounted or downloaded at
runtime and are never copied into images.

The `validator` image is a small working example:

```bash
docker build -f docker/validator/Dockerfile -t lite-rsi-validator .
docker run --rm -v "$PWD:/workspace:ro" lite-rsi-validator /workspace
```

Evaluation images should eventually be published using versioned names such as:

```text
ghcr.io/haolpku/lite-rsi-llm:0.1.0
ghcr.io/haolpku/lite-rsi-multimodal:0.1.0
ghcr.io/haolpku/lite-rsi-generative:0.1.0
```

Verified result manifests should pin an image digest rather than `latest`.
Document required host drivers, minimum memory, supported architectures, mounted
paths, runtime secrets, and a smoke-test command beside every environment.

