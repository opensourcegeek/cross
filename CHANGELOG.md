# Change Log

All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]

### Added

- `cross run` support for the thumb targets.

- A `build.xargo` / `target.$TARGET.xargo` option to Cross.toml to use Xargo
  instead of Cargo.

- A `target.$TARGET.image` option to override the Docker image used for
  `$TARGET`.

- A `sparc64-unknown-linux-gnu` environment.

- A `x86_64-unknown-dragonfly` environment .

## [v0.1.4] - 2017-01-07

### Added

- Support for the `arm-unknown-linux-gnueabi` target

- `cross build` support for:
  - `i686-unknown-freebsd`
  - `x86_64-unknown-freebsd`
  - `x86_64-unknown-netbsd`

### Changed

- It's no longer necessary to call `cargo generate-lockfile` before using
  `cross` as `cross` will now take care of creating a lockfile when necessary.

- The C environments for the `thumb` targets now include newlib (`libc.a`,
  `libm.a`, etc.)

### Fixed

- A segfault when `cross` was trying to figure out the name of the user that
  called it.

## [v0.1.3] - 2017-01-01

### Changed

- Fix the `i686-unknown-linux-musl` target

## [v0.1.2] - 2016-12-31

### Added

- Support for `i686-unknown-linux-musl`
- Support for `cross build`ing crates for the `thumbv*-none-eabi*` targets.

## [v0.1.1] - 2016-12-28

### Added

- Support for `x86_64-unknown-linux-musl`
- Print shell commands when the verbose flag is used.
- Support crossing from x86_64 osx to i686 osx

## v0.1.0 - 2016-12-26

- Initial release. Supports 12 targets.

[Unreleased]: https://github.com/japaric/cross/compare/v0.1.4...HEAD
[v0.1.4]: https://github.com/japaric/cross/compare/v0.1.3...v0.1.4
[v0.1.3]: https://github.com/japaric/cross/compare/v0.1.2...v0.1.3
[v0.1.2]: https://github.com/japaric/cross/compare/v0.1.1...v0.1.2
[v0.1.1]: https://github.com/japaric/cross/compare/v0.1.0...v0.1.1
