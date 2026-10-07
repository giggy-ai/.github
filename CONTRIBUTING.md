# Contributing to Giggy

Thanks for contributing to Giggy's public developer tools.

## Scope

Giggy's public GitHub repositories contain SDKs, runnable integration examples, and MCP documentation. The production API contract is maintained separately; do not introduce API behavior changes through these repositories.

## Contributions

1. Open an issue describing the proposed change when appropriate.
2. Keep changes scoped.
3. Add or update tests for behavioral changes.
4. Update documentation when public usage changes.
5. Do not commit API keys or generated speech output.

## Validation

For JavaScript SDK changes, run `npm ci` and `npm test`. For Python SDK changes, run `python -m unittest discover -s tests -v`. For integration examples, run the relevant repository checks. Real synthesis tests may require credentials and may consume credits.
