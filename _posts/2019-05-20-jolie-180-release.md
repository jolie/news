---
layout: post
author: Fabrizio Montesi
title: Jolie 1.8.0 released
tags:
- jolie
- microservices
- release
---

Jolie 1.8.0 has been released. Get it from [https://jolie-lang.org/downloads.html](https://jolie-lang.org/downloads.html).

This is a pretty big release, containing many aesthetic and useful improvements. Read up for the full changelog.

All changes are backwards-compatible, no need to worry about your existing Jolie code.

# Changelog

### Bye bye semicolons

Ending statements with semicolons in sequential compositions is no longer necessary.

Before:

```jolie
msg = "Hello, world!";
println@Console( msg )();
// etc.
```

After:

```jolie
msg = "Hello, world!"
println@Console( msg )()
// etc.
```

### Simplified type syntax

When defining data types, dots in front of subnodes are now optional.
Defining the type of node values is now optional, with `void` being the default.

Before:

```jolie
type Team:void {
	.name:string
	.member[1,10]:void {
		.name:string
		.age:int
	}
}
```

After:

```jolie
type Team {
	name:string
	member[1,10] {
		name:string
		age:int
	}
}
```


### Improved tree literals

Tree literals have been improved: they now support nested trees, deep copy operations, and aliasing.
Dots (to prefix subnodes) and commas (to separate nodes) are now optional.
You can still use paths inside of tree literals to point to deeply-nested nodes.

For example, you can now rewrite this

```jolie
config.username = "jolie"
config.server.uri = "https://jolie-lang.org/"
config.resource = "/news"
config.protocol.name = "https"
config.protocol.version = "TLSv1.3"
```

into

```jolie
config << {
	username = "jolie"
	server.uri = "https://jolie-lang.org/"
	resource = "/news"
	protocol << {
		name = "https"
		version = "TLSv1.3"
	}
}
```

### Casing in ports

The nodes `Location`, `Protocol`, and `Interfaces` in communication ports can also be spelled `location`, `protocol`, and `interfaces` now, respectively, to be consistent with the rest of the language.

Before:

```jolie
outputPort SomeServer {
Location: "socket://localhost:8080"
Protocol: sodep
Interfaces: MyInterface1, MyInterface2
}
```

After:

```jolie
outputPort SomeServer {
	location: "socket://localhost:8080"
	protocol: sodep
	interfaces: MyInterface1, MyInterface2
}
```

### Other changes

- A new `--responseTimeout` command line parameter to set a global timeout for all solicit-response invocations (see `jolie --help`).
- Pretty printing values now prints Jolie types, instead of their Java type correspondent.
- Bugfix for equality check of choice types.
- Various resource leak fixes: LGTM.com now detects no issues.
- Bugfix in querystring generation, now there are no more trailing ampersands.
- Fixed an NPE when type checking courier processes.
- The standard library service for sending e-mails now supports multiple attachments.
- Standard library:
	* New operation: `getVersion@Runtime`
	* `md5@MessageDigest` can now take byte arrays as input.
