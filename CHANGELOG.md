# Changelog

All notable changes to `coolms/entity-module` are recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning is described in `CONTRIBUTING.md` -- read it before assuming what a
major number means here.

⚠️ Entries dated before 2026-09-01 were **reconstructed** from tags and commit
history when this file was created. Every entry after that is written in the
same commit as the change it describes.

## Unreleased -- 2.1.0

Rides the next Tuesday release train. Nothing here has shipped yet.

### Changed: sibling constraints move to the v2 generation

- `coolms/core`: `^1.0` to `^2.0`
- `coolms/entity`: `^1.0` to `^2.0`
- `coolms/entity-persistence-implementation`: `^1.0` to `^2.0`
- `coolms/entity-doctrine` (development): `^1.0` to `^2.0`

⚠️ **This is a minor, not a major, and that is deliberate.** This package
reached major 2 before the platform adopted a shared generation number, and it
did so while still requiring major 1 of its siblings. The v2 generation of those
siblings is **code-identical** to v1 -- their major moved to mark the
generation, not to break anything -- so nothing a caller can reach has changed
here.

**Upgrading:** if your own `composer.json` pins any of those packages at
`^1.0`, widen it to `^2.0`. Otherwise there is nothing to do.

The constraints on `coolms/dtmpl` and `coolms/rql` are unchanged. Those are
standalone libraries and do not take the platform generation.

## 2.0.0 - 2026-08-26

### Changed

Require `coolms/dtmpl` `^2.0`. DTMPL 2.0 encodes output by default and renamed
the verbatim block; a major here rather than a minor because moving a consumer
across that boundary is a break for them, whether or not this package's own API
moved.

Also added the CI, version, PHP and licence badges to the readme.

## 1.0.0 - 2026-08-18

First release. The platform composition layer over `coolms/entity`: reflection
field extraction, the tagged repository registry, the extras-flattening
normalizer, and the `entity:find` widget renderers.
