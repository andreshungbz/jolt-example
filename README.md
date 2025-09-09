# jolt-example

Jolt GitHub Repository: https://github.com/vasiltop/jolt

## Dev Container

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1053728315)

The dev container configuration uses `/.devcontainer/Dockerfile` to build the container using the x86_64 Microsoft C++ Ubuntu 24.04 base image, and installs LLVM 16 and other needed tools.

The following `postCreateCommand` configured in `/.devcontainer/devcontainer.json` clones the Jolt repository (deleting it if it already exists), replaces the appropriate lines in the Makefile, and then runs `make` to build the Jolt compiler. The resulting binary is in the following path: `/jolt/bin/compiler`.

## Using the Jolt Compiler

From the root repository, you can run the following, which gives you three files `out`, `out.ll`, and `out.o`:

```
./jolt/bin/compiler hello.jl ./a.out
```

Run the compiled binary:

```
./out
```

## Building the Jolt Compiler (Manual)

- LLVM 15 or 16 and related C++ tools.
- x86_64 build-essentials
- Edit the jolt repository Makefile so that instead of `llvm-config`, it is `llvm-config-15` or `llvm-config-16` depending on your LLVM version.
