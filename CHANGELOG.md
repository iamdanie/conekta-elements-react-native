# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Fixed

- iOS install: the XCFramework download pointed at `github.com/conekta/conekta-elements/releases`, which returns 404, so `npm install` and `pod install` failed. It now downloads from the public [conekta-components-ios](https://github.com/conekta/conekta-components-ios) releases (`1.1.0-beta.31`, sha256-checked).
- The download script and podspec use `curl -f`, so an HTTP error fails with a clear message instead of a checksum mismatch.

### Changed

- iOS now uses Conekta Components `1.1.0-beta.31`, which requires iOS 15.0 (was 14.0).
- Android now uses `io.conekta:conekta-elements-compose` `1.0.0` (was `0.2.0-beta.2`).
- `package.json` `conektaElements` has separate `androidVersion` and `iosVersion`, since the two platforms are released separately.

## [0.0.1] - 2026-03-03

First stable release of `conekta-elements-react-native` on the public npm registry.

### Added

- `<ConektaTokenizer />` component that renders the native Conekta Elements Compose UI on Android and iOS
- Automatic XCFramework download via `postinstall` script for iOS
- Android autolinking support (no manual configuration required)
- TypeScript types for `TokenizerConfig`, `TokenResult`, and `TokenizerError`
- Expo development build compatibility (Expo Go is not supported)
- CI workflow for publishing to npm on GitHub releases
- PR validation workflow with type checking

