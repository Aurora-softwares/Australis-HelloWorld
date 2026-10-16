# Australis Hello World

## Current status

The source prints `Hello, World!` and exits successfully. This is a minimal AUEX application, not a shell or service.

`HelloWorld.hyproj` builds `hello-world.exec`. The Australis OS aggregate includes
this project and installs the executable at `/System/Bin/hello-world.exec` in the read-only
HyFS 2 boot image. Run it by its bare name `/System/Bin/` through the current
recovery shell's `PATH`, or use `run /System/Bin/hello-world.exec`.

## Planned direction

Keep it as a small build and launch example while OS commands move into separate userland projects.

Build this checkout with:

```bash
mkdir -p build
hy build HelloWorld.hyproj -o build/hello-world.exec
```

AUEX `.exec` files currently run in the checked interpreter. Native ring-3
processes and a normal userland shell are later milestones. The boot root is
read-only; writable application data belongs on the separate `/data` volume.
The OS-level build, supported APIs, and packaging rules are described in the
Australis OS `applications/README.md`. This README describes this project's
actual source rather than treating its filename as proof of a finished feature.
