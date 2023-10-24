# nzws/prisma-rpi-builds

This repository is a fork of https://github.com/pantharshit00/prisma-rpi-builds that is maintained in 2023.
I also recommend using a 64bit RPi OS, but I built this binary for some environments where a clean install is not possible (like me).

---

## Prisma precompiled builds for Raspberry Pi (armv7)

This repository contains precompiled [prisma-engines](https://github.com/prisma/prisma-engines) for Raspberry Pi.

## How to use this repository

(This mostly follows this documentation piece, please read this once: https://www.prisma.io/docs/concepts/components/prisma-engines#using-custom-engine-binaries)

1. Download all 3 Engine files from this repository's GitHub releases page: https://github.com/nzws/prisma-rpi-builds/releases
2. Put all the downloaded files into a folder in your project
3. Make sure all 2 binaries are executable using `chmod +x <binary path>`
4. Set the following environment variables in your shell or in the `.env` file: (_edit: Due to changes on the Prisma, the required binaries are different than before_)
   ```sh
   PRISMA_QUERY_ENGINE_BINARY=/path/to/query-engine
   PRISMA_QUERY_ENGINE_LIBRARY=/path/to/libquery_engine_napi.so.node
   PRISMA_SCHEMA_ENGINE_BINARY=/path/to/schema-engine
   ```
5. You are now ready to use Prisma on your Raspberry Pi.

## Additional notes

CI in this repository checks for a new major Prisma version everyday and if there is a new release avaliable, it will automatically build the engines and make a new release.
