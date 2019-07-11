---
layout: post
author: Fabrizio Montesi
title: Jolie 1.8.1 released
tags:
- jolie
- microservices
- release
- code
- vscode
---

Jolie 1.8.1 has been released. Get it from [https://jolie-lang.org/downloads.html](https://jolie-lang.org/downloads.html).

This is the first stable release that supports our new official Visual Studio Code extension for Jolie: [https://marketplace.visualstudio.com/items?itemName=jolie.vscode-jolie](https://marketplace.visualstudio.com/items?itemName=jolie.vscode-jolie)

# Changelog

- The biggest change is the introduction of a new `Inspector` service to the standard library. This service provides code inspection operations for analysing Jolie source code, which is used in the implementation of the Language Server Protocol used in the new Visual Studio Code extension for Jolie.
- Improvements and bugfixes for the `jsonrpc` protocol.
- Bugfixes for the redirection feature.
- Field `end` in `substring@StringUtils` is now optional (defaults to the length of the string).
