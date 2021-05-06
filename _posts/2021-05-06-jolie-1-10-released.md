---
layout: post
author: Fabrizio Montesi
title: Jolie 1.10.0 released
tags:
- jolie
- microservices
- release
---

Jolie 1.10.0 has been released. Get it from [https://jolie-lang.org/downloads.html](https://jolie-lang.org/downloads.html).

# Changelog

- **New module system.** Jolie now offers a [module system](https://docs.jolie-lang.org/v1.10.x/language-tools-and-standard-library/basics/modules.html), inspired by Python's `from .. import ..` mechanism. The general principle is to keep keeps things simple and provide (often automatic) facilities to avoid namespace pollution.
- **New service block.** Services are now syntactically manifest thanks to a new `service` construct. Services can take parameters, either programmatically or from externally-provided files.
- **New foreign service syntax.** Foreign services (services implemented in Java or JavaScript instead of Jolie) are now implemented by hiding the implementation technology from embedders, allowing for more reusable code (changing how a service is implemented does not alter the orchestrator that loads it through embedding).
- **Message ids.** Message ids in Jolie now adopt a snowflake-like mechanism for their network-wide tracking.
- **Maven Central.** The Jolie libraries for developing Java Services and Jolie code analysis tools are now available on Maven Central (look for the group id `org.jolie-lang`).
- **Semantics improvements.** Arithmetic operators are now commutative under implicit type casts (<https://github.com/jolie/jolie/issues/232>). A concurrency bug of the `for .. in ..` construct has been fixed.
- **HTTP.** The `http` protocol now allows for arbitrary header read/write.
- **Bug fixes.** Numerous bug fixes to HTTP, fault management, and Java services.
- **Code of Conduct.** Jolie has joined the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/1/4/code-of-conduct.html).
