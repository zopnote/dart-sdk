## Modified Dart SDK for cross compilation support
The ``dartcc-sdk`` just took some changes in the build pipeline.

With ``create_cc_all`` you can build all binaries, available on this platform.
In the releases tab you will find binary kits, which consist of all required binaries 
to support cross compilation on the taken host.

Dart is:

  * **Approachable**:
  Develop with a strongly typed programming language that is consistent,
  concise, and offers modern language features like null safety and patterns.

  * **Portable**:
  Compile to ARM, x64, or RISC-V machine code for mobile, desktop, and backend.
  Compile to JavaScript or WebAssembly for the web.

  * **Productive**:
  Make changes iteratively: use hot reload to see the result instantly in your running app.
  Diagnose app issues using [DevTools](https://dart.dev/tools/dart-devtools).
---
![Dart platforms illustration](docs/assets/Dart-platforms.svg)

## Building

[Getting the source, preparing your machine to build the SDK, and building][building], then just pick the ``create_cc_all`` target.

## Roadmap

Future plans for Dart are included in the combined Dart and Flutter
[roadmap][roadmap] on the Flutter wiki.
