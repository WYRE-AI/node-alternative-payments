## [1.0.2](https://github.com/WYRE-AI/node-alternative-payments/compare/v1.0.1...v1.0.2) (2026-08-25)


### Bug Fixes

* migrate to WYRE-AI org (npm scope, ghcr namespace, registry) ([#16](https://github.com/WYRE-AI/node-alternative-payments/issues/16)) ([09bd71e](https://github.com/WYRE-AI/node-alternative-payments/commit/09bd71ea5a2e579e3799e9084aa336539c38e7f4))

## [1.0.1](https://github.com/WYRE-AI/node-alternative-payments/compare/v1.0.0...v1.0.1) (2026-08-13)


### Bug Fixes

* **deps:** re-pin typescript to ^6.0.3 + ignoreDeprecations, add explicit types:node ([#12](https://github.com/WYRE-AI/node-alternative-payments/issues/12)) ([2efdc0e](https://github.com/WYRE-AI/node-alternative-payments/commit/2efdc0e1d6b9c50b9d0a0b7956df90c8de8badfb)), closes [node-kaseya-quote-manager#7](https://github.com/node-kaseya-quote-manager/issues/7) [blackpoint-mcp#44](https://github.com/blackpoint-mcp/issues/44)

# 1.0.0 (2026-06-05)


### Features

* initial Alternative Payments SDK ([1c82a66](https://github.com/WYRE-AI/node-alternative-payments/commit/1c82a667e14c7dc7190aa20c147082add7af10b0))

# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- **Release workflow no longer persists a write-scoped git credential across `npm ci`.** The release job declares `contents: write`, which overrides this repo's read-only default workflow permission, so `actions/checkout`'s default persisted credential was write-scoped and lived in `.git/config` through dependency install, build and test — readable by any compromised dependency lifecycle script. `persist-credentials: false` is semantic-release's own documented GitHub Actions recipe; it authenticates its pushes from `GITHUB_TOKEN` directly and never needed the persisted credential. (CWE-250, flagged by CodeRabbit.)


- Initial release of the Alternative Payments Node.js/TypeScript SDK.
- OAuth 2.0 client-credentials token manager with automatic refresh.
- Sliding-window rate limiter (5 req/s default) and retry-with-backoff.
- Resources: customers, invoices, transactions, payment requests, payouts, webhooks.
- Typed error hierarchy (`AuthenticationError`, `ValidationError`, `RateLimitError`, etc.).
