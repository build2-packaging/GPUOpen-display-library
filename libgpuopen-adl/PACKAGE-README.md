# libgpuopen-adl - AMD Display Library SDK C library

This is a `build2` package for the
[`display-library`](https://github.com/GPUOpen-LibrariesAndSDKs/display-library)
C library. It provides the AMD Display Library SDK. The majority of the APIs
in ADL wrap the company's private APIs thus allowing the library's client to
access information related to the graphics associated with the system.

This package is licensed under the MIT License, as stated in each of the
upstream headers. Note that upstream also refers to the
[ADL SDK EULA](https://raw.githubusercontent.com/GPUOpen-LibrariesAndSDKs/display-library/18.0/Public-Documents/ADL%20SDK%20EULA.pdf)
for the SDK as a whole (see
[issue #41](https://github.com/GPUOpen-LibrariesAndSDKs/display-library/issues/41)).


## Usage

To start using `libgpuopen-adl` in your project, add the following `depends`
value to your `manifest`, adjusting the version constraint as appropriate:

```
depends: libgpuopen-adl ^18.0.0
```

Then import the library in your `buildfile`:

```
import libs = libgpuopen-adl%lib{gpuopen-adl}
```


## Importable targets

This package provides the following importable targets:

```
lib{gpuopen-adl}
```

The ADL SDK headers, included without a subdirectory prefix
(`#include <adl_sdk.h>`, which includes `adl_structures.h` and
`adl_defines.h`). The package version is the ADL SDK version (`18.0.0` is
ADL SDK 18.0).

This library is header-only. The ADL implementation is part of the AMD
display driver (`atiadlxx.dll`, or `atiadlxy.dll` for 32-bit applications on
64-bit Windows) and the headers do not declare its functions. Instead, load
the ADL DLL at runtime with `LoadLibrary()` and resolve the functions with
`GetProcAddress()` using function pointer types declared by the application,
as in the upstream samples.

As in upstream, the headers target Windows. In C, they rely on `wchar_t`
being already declared (for example, by including `<stddef.h>` before
`<adl_sdk.h>`).


## Configuration variables

This package provides no configuration variables.
