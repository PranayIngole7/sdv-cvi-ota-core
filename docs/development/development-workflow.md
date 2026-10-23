# Development Workflow

## Feature Lifecycle

1. Define the problem and acceptance criteria.
2. Explain the rationale and design.
3. Implement the smallest coherent change.
4. Run automated tests and relevant quality checks.
5. Exercise failure cases and inspect actual behavior.
6. Fix defects and review security implications.
7. Update product and operational documentation.
8. Record verified evidence and release readiness.

## Git Practices

- Keep `main` releasable.
- Use focused, descriptive commits.
- Never commit credentials, tokens, private keys, or local environment files.
- Do not create a release tag until acceptance criteria and checks pass.
- Review `git status` and the diff before committing.

## Verification

Document the exact commands used and their actual results. Do not describe
untested behavior as working or production-ready.
