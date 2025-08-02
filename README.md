## Modified Dart SDK for cross compilation support
The ``dartcc-sdk`` just took some changes in the build pipeline.

With ``create_cc_all`` you can build all binaries, available on this platform.
In the releases tab you will find binary kits, which consist of all required binaries 
to support cross compilation on the taken host.

## In depth information about embedding the binaries
There are three binaries required to build a self-contained executable for desktop targets. 
For mobile there also have to be an embedder. Under ``samples/embedder`` is an embedder currently developed as part of the sdk. 
Furthermore, this fork belongs to ``dartcc``, an advanced Dart compiler, which also implements an embedder for mobile devices.

The three binaries are:
* ``gen_snapshot_<platform>`` executable (run on host)
* ``gen_kernel_<platform>.aot`` snapshot (run on host)
* ``aotruntime_<platform>`` executable (run on target)

The ``gen_kernel`` binary have to be compiled on the host platform, can only run on the host platform and will generate
cross-platform or platform-dependent kernel snapshots.
Based on the configurations the produced kernel can be used
with the ``gen_snapshot`` tool to produce binary blobs.

The ``gen_snapshot`` binary have to be compiled on the host platform, can only run on the host platform and will only
generate code for the target platform.
It generates 3 different binary blobs, data about the kernel, the isolate and code.

The binary blobs need an ``aotruntime`` to work properly on the desired platform.
The 3 binaries will be linked with the runtime to create a self-contained executable on desktop.
For mobile another piece have to come together. The runtime has then to be embedded 
into a C/C++ application that uses the Dart C and, for additional features the Dart C++ interfaces.