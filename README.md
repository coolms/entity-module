# coolms/entity-module

[![CI](https://github.com/coolms/entity-module/actions/workflows/ci.yml/badge.svg)](https://github.com/coolms/entity-module/actions/workflows/ci.yml)
[![Latest Version](https://img.shields.io/packagist/v/coolms/entity-module)](https://packagist.org/packages/coolms/entity-module)
[![PHP](https://img.shields.io/badge/php-%E2%89%A5%208.5-777bb4)](https://www.php.net/releases/8.5/en.php)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

Platform composition over [`coolms/entity`](https://packagist.org/packages/coolms/entity):
the pieces that need a persistence implementation without naming one.

- `Serializer\ExtrasFlatteningNormalizer` -- lifts an entity's `$extras` bag onto
  the normalized top level and routes writes back into it, filtered by the
  instance-aware schema so a field scoped with `appliesTo` never leaks onto an
  instance it does not apply to. Types claimed through
  `ExtrasNormalizationExclusionInterface` are left alone.
- `TaggedRepositoryRegistry` / `Resolver\RepositoryEntityAliasResolver` --
  alias-to-repository lookup over the tagged repository set.
- `ReflectionFieldExtractor` / `Field\ReflectionEntityFieldDescriptor` --
  attribute-driven field description.
- `Widget\*` -- `entity:find` and `entity:findAll` renderers for coolms/dtmpl.

Requires the virtual package `coolms/entity-persistence-implementation`, which
`coolms/entity-doctrine` provides.

## Installation

```bash
composer require coolms/entity-module
```
