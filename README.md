# SimpleWebAuthn <!-- omit in toc -->

![WebAuthn](https://img.shields.io/badge/WebAuthn-Simplified-blueviolet?style=for-the-badge&logo=WebAuthn)
[![JSR Scope](https://jsr.io/badges/@simplewebauthn?style=for-the-badge)](https://jsr.io/@simplewebauthn)

- [Overview](#overview)
- [Installation](#installation)
- [Documentation](#documentation)
- [Contributions](#contributions)
- [Development](#development)

## Overview

This project features two complimentary libraries to help reduce the amount of work needed to
incorporate WebAuthn into a website. The following packages are maintained here:

- [@simplewebauthn/server](https://github.com/transeptorlabs/SimpleWebAuthn/tree/feature/prf-support/packages/server)
- [@simplewebauthn/browser](https://github.com/transeptorlabs/SimpleWebAuthn/tree/feature/prf-support/packages/browser)

## Installation

SimpleWebAuthn can be installed from **[NPM](https://www.npmjs.com/search?q=%40simplewebauthn)** and
**[JSR](https://jsr.io/@simplewebauthn)** in **Node LTS 20.x and higher**, **Deno v1.43 and higher**
projects, and other compatible runtimes (Cloudflare Workers, Bun, etc...)

See the packages' READMEs for more specific installation information.

## Documentation

In-depth documentation for this project is available at https://simplewebauthn.dev/docs

> Note: No external documentation will be produced for PRF extension feature.

## Contributions

The SimpleWebAuthn fork project to enable support for PRF extension is not currently open to external contributions.

Please [submit an Issue upstream](https://github.com/MasterKale/SimpleWebAuthn/issues/new/choose) and fill
out the provided template with as much information as possible if you have found a bug in need of
fixing.

You can also [submit an Issue upstream](https://github.com/MasterKale/SimpleWebAuthn/issues/new/choose) to
request new features, or to suggest changes to existing features.

## Development

Install the following before proceeding:

- **Deno v2.1.x**

After pulling down the code, set up dependencies:

```sh
$> deno install
```

To run unit tests for all workspace packages, use the `test` series of scripts:

```sh
# Run an individual package's tests
$> cd packages/browser/ && deno task test
$> cd packages/server/ && deno task test
```

Tests can be run in watch mode with the `test:watch` series of scripts:

```sh
$> cd packages/browser/ && deno task test:watch
$> cd packages/server/ && deno task test:watch
```
