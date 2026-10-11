# GPUOpen-display-library - AMD Display Library SDK C library

This is a `build2` package repository for
[`display-library`](https://github.com/GPUOpen-LibrariesAndSDKs/display-library),
the AMD Display Library SDK.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`libgpuopen-adl` in your `build2`-based project, then instead see the accompanying
[`PACKAGE-README.md`](libgpuopen-adl/PACKAGE-README.md) file.

The development setup for `GPUOpen-display-library` uses the standard `bdep`-based workflow.
For example:

```
git clone --recurse-submodules https://github.com/build2-packaging/GPUOpen-display-library.git
cd GPUOpen-display-library

bdep init -C @msvc cc config.c=cl
bdep update
bdep test
```
