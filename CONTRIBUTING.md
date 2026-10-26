# Contributing to Ky

These testing and warning requirements apply across the Busnes.app Ky
repositories. Follow each product's contributor guide for setup, commands,
security boundaries and platform-specific checks.

## Automated tests

Major new functionality must include tests in an automated test suite. Run the
affected checks during development and the repository's required full checks
before hand-back. Record the commands, results and any skipped checks in the
pull request. A passing local fixture does not establish production or
integration readiness beyond what that fixture checks.

## Compiler and linter warnings

Fix valid compiler and linter warnings. If a warning is a false positive,
document the reason in the relevant source or check configuration so reviewers
can assess it. Do not silently ignore warnings.

## Proposing a change

Use the product's issue tracker and pull-request process. Describe the user
effect, verification and material limitations. Update the owning documentation
when behavior or operating requirements change. Report vulnerabilities privately
through [SECURITY.md](SECURITY.md).
