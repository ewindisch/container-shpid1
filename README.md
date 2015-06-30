sh for init
-----------

When building Docker images, it's not uncommon for users
to spawn a pid-1 process which is, ultimately, bash
or a POSIX sh. This can lead to the "pid 1" problem where
SIGTERM is not properly handled.

Having seen many Docker images where this is not handled at all,
or handled incorrectly, I've decided it would be best to share
this with the world as a snippet that may be used as a library.

This script should be posix-sh compatible and any failing of that
may be filed as a bug. Pull requests are accepted.

Usage:
------

There are several options in using this library:

1) Library: Copy this to your $PATH and use the following:

```
#!/bin/sh
. $(which shpid1)

# Your script here.
```

Alternatively, skip 'which' and put this into a static path
known to your own script(s).

2) Vendor: Copy the contents of this script into your own:

```
cat shpid1 yourscript.sh > newscript.sh
```

License:
--------
The MIT License (MIT), Eric Windisch
See LICENSE file for text.
