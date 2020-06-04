---
layout: post
author: Fabrizio Montesi
title: Jolie 1.9.1 released
tags:
- jolie
- microservices
- release
---

Jolie 1.9.1 has been released. Get it from [https://jolie-lang.org/downloads.html](https://jolie-lang.org/downloads.html).

## Support for shebang in scripts

You can now use Jolie as a scripting language in Linux and macOS.

```jolie
#!/usr/bin/env jolie

include "console.iol"

main {
	println@Console( "Hello, Jolie!" )()
}
```

## Windows fixes

There are numerous fixes to the Jolie interpreter and installer to deal with paths in Windows, which resolve a few situations found with Jolie 1.9.0.

## Other changes

- Fix to the behaviour of fault handlers, which in some situations prevented escape from the current fault management scope from within a fault handler.
- Improved parsing error messages for types that use the new syntax without the `.` prefix.
- Better error management of invalid paths in all OSs.
