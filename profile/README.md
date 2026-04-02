# Zoe Foundation

Zoe is an open-source attempt to make photo and video provenance more practical for real users.

The project is focused on a narrow claim: a file was captured through the Zoe workflow on Apple hardware, and the file has not changed since Zoe signed it. It is not trying to prove that a scene was truthful, unstaged, or free from context manipulation.

## What problem Zoe tries to solve

Digital media is easy to copy, edit, and repost without trustworthy context. Zoe explores a simpler answer to that problem:

- capture media inside a dedicated iOS app
- create a device-bound signing key in the Secure Enclave
- register that device with Apple App Attest
- generate a signed proof bundle for the final file
- verify that proof later against the backend

## How Zoe works

![Zoe platform flow](./platform-flow.svg)

In practice, Zoe is split into two public codebases:

- [zoe-ios](https://github.com/zoefoundation/zoe-ios): the iPhone app for capture, signing, library management, and verification
- [zoe-backend](https://github.com/zoefoundation/zoe-backend): the FastAPI and PostgreSQL backend for registration, proof storage, and verification

You can also see the public site at [zoe-foundation.web.app](https://zoe-foundation.web.app).

## Current direction

Zoe is still an early-stage prototype. The current architecture is built around detached proof bundles, server-backed verification, and a deliberately limited trust model rather than broad claims about "truth" in media.
