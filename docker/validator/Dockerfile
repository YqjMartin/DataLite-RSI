FROM python:3.11-slim@sha256:db3ff2e1800a8581e2c48a27c3995339d47bdf046da21c7627accd3d51053a93

LABEL org.opencontainers.image.source="https://github.com/haolpku/Lite-RSI"
LABEL org.opencontainers.image.description="Lite-RSI contribution manifest validator"

WORKDIR /workspace
COPY scripts/validate_contributions.py /opt/lite-rsi/validate_contributions.py

USER 65532:65532

ENTRYPOINT ["python", "/opt/lite-rsi/validate_contributions.py"]
CMD ["/workspace"]
