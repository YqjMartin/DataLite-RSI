## Contribution type

- [ ] Benchmark
- [ ] Dataset registration
- [ ] Experimental result
- [ ] RSI method or code
- [ ] Evaluation/Docker infrastructure
- [ ] Documentation or maintenance

## Summary

Explain the scientific motivation and the user-visible change.

## Reproduction or validation

List the exact commands used to test this change. For results, include the
benchmark, code revision, dataset revision, container image, settings, and
artifact location.

```bash
python scripts/validate_contributions.py .
python -m unittest discover -s tests -v
```

## Checklist

- [ ] The PR has one clear primary purpose.
- [ ] Relevant manifests, documentation, and tests are included.
- [ ] Manifest IDs match their directory names.
- [ ] Data and container references use pinned versions or revisions.
- [ ] Licenses, provenance, privacy, and known limitations are documented.
- [ ] No secrets, private data, model weights, dataset archives, or large
      generated artifacts are committed.
- [ ] I disclosed failed/excluded runs and human intervention where applicable.

## Related issues

Closes #

