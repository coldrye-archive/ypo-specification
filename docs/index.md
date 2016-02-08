# YPO File Format Specification


## Table of Contents

1. [Introduction](#introduction)
2. Concepts
  1. [Translation Unit](./unit.md)
  2. [Translation](./translation.md)
  3. [Variation](./variation.md)
  4. [Text](./text.md)
3. Addendum
  1. [Addendum - Production Rules](./addendum-rules.md)


## Introduction

The YPO file format is indented to be used as an alternative for authoring
i18next translation units using a plain text file format instead of JSON.


### Intended Audience

The provided specification is intended for use by both developers and
translators.


### Standard File Extension

The standard file extension is `.ypo`.


### Encoding

The default encoding is UTF-8. The number of supported encordings is currently
being limited by ``node`` platform, yet, and as the available tooling evolves,
additional encodings will become available.


### Line Separators

All available line separators, e.g. '\n', '\r', and '\r\n' are supported.


### Motivation

Simply put, authoring i18next JSON files using VI is very tedious.
Likewise so is authoring gettext PO files. And while the latter is much
more streamlined than i18next JSON, it is still rather cumbersome when
authoring plurals a/o contexts in combination with i18next.


### Limitations and Otherwise Unsupported Features


#### i18nextv2: Arrays and Trees

We are unable to find any use case for any of the two, and what cannot be
expressed by using standard translation ids a/o variations thereof.

Also, we do not believe in i18next to behave as a database other than providing
translations for a given input key, provably contextualized and provably also
in need of pluralization.

TODO:example for replacing arrays using standard keys and variations thereof
TODO:example for replacing trees using standard keys and variations thereof


#### i18nextv2: Interval Plurals

While this is definitely a feature to go for, the current i18next specification
makes it rather difficult to maintain interval variations, given that all
information must be squeezed into a single string.

For the time being, just use carefully designed plural variations.

TODO:example for replacing interval plurals using standard plurals


#### i18nextv2: Fallback Keys

Having text as the translation id is rather cumbersome and might never be supported.
While having used gettext in both django/python and c/c++ based projects, we believe
that simple identifiers are much more efficient in a Javascript environment.


#### gettextPO: Extracted Comments

Comments are already supported and the tooling might evolve to the point that
it will be able to extract related comments from the sources.

For now, comments in YPO files need to be maintained manually.


#### gettextPO: Source References

Source references are currently not part of the specification. As the tooling
evolves, these might become part of the specification.

