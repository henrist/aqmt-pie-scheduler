# pie scheduler for aqmt

This repository contains the PIE scheduler from Linux patched so
it can be used with https://github.com/henrist/aqmt

New commits in Linux should be cherry-picked to the `kernel-reference`
branch and merged to master. This way the `kernel-reference` should
be a 1-to-1 match to the implementation in Linux.

## Using

When building, we need to add the `common` directory of the `aqmt`
repository to the inclusion path.

Building:

```
CPATH=/path/to/aqmt/common make
```

Loading kernel module:

```
sudo make load
```

The scheduler will now be available as a qdisc with the name `pie`.
Note that if you had `pie` available already this will shadow that
module, so this will be used instead.

Unloading:

```
sudo make unload
```
