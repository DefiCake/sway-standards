<p align="center">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset=".docs/sway-standards-logo-dark-theme.png">
        <img alt="Sway Standards logo" width="400px" src=".docs/sway-standards-logo-light-theme.png">
    </picture>
</p>

<p align="center">
    <a href="https://github.com/FuelLabs/sway-standards/actions/workflows/ci.yml" alt="CI">
        <img src="https://github.com/FuelLabs/sway-standards/actions/workflows/ci.yml/badge.svg" />
    </a>
    <a href="https://crates.io/crates/forc/0.46.0" alt="forc">
        <img src="https://img.shields.io/badge/forc-v0.46.0-orange" />
    </a>
    <a href="./LICENSE" alt="forc">
        <img src="https://img.shields.io/github/license/FuelLabs/sway-standards" />
    </a>
    <a href="https://discord.gg/xfpK4Pe">
        <img src="https://img.shields.io/discord/732892373507375164?color=6A7EC2&logo=discord&logoColor=ffffff&labelColor=6A7EC2&label=Discord" />
    </a>
</p>

## Overview

The purpose of this repository is to contain standards for the Sway Language which users can import and use. 

Standards in this repository may be in various stages of development. Use of draft standards and feedback on the proposed standards is encouraged. To use a draft, search for a standard using the appropriate GitHub label and implement the standard abi into your contract. 

If you don't find what you're looking for, feel free to create an issue and propose a new standard!

> **Note**
> Sway is a language under heavy development therefore the standards may not be the most ergonomic. Over time they should receive updates / improvements in order to demonstrate how Sway can be used in real use cases.

## Standards

- [SRC-20; Token Standard](./standards/src_20/) defines the implementation of a standard API for [Native Assets](https://fuellabs.github.io/sway/v0.44.0/book/blockchain-development/native_assets.html) using the Sway Language.
- [SRC-2; Inline Documentation](./standards/src_2/) defines how to document your Sway files.
- [SRC-3; Mint and Burn](./standards/src_3/) is used to enable mint and burn functionality for Native Assets.
- [SRC-5; Ownership Standard](./standards/src_5/) is used to restrict function calls to admin users in contracts.
- [SRC-7; Arbitrary Asset Metadata Standard](./standards/src_7/) is used to store metadata for [Native Assets](https://fuellabs.github.io/sway/v0.44.0/book/blockchain-development/native_assets.html).

## Using a standard

To import a standard the following should be added to the project's `Forc.toml` file under `[dependencies]` with the most recent release:

```rust
standard = { git = "https://github.com/FuelLabs/sway-standards", tag = "v0.1.0" }
```

You may then import your desired standard in your Sway Smart Contract as so:

```rust
use standard::<standard_abi>;
```

For example, to import the SRC-20 Token Standard use the following statements in your `Forc.toml` and Sway Smart Contract file respectively:

```rust
src_20 = { git = "https://github.com/FuelLabs/sway-standards", tag = "v0.1.1" }
```

```rust
use src_20::SRC20;
```

> **Note**
> All standards currently use `forc v0.46.0`.

<!-- TODO:
## Contributing

Check out the [book](https://fuellabs.github.io/sway-libs/book/index.html) for more info! 
-->

> **Note**
> The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in these documents are to be interpreted as described in RFC 2119: https://www.ietf.org/rfc/rfc2119.txt
