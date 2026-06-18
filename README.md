# Nginx Multi-Distro Build

This repository provides GitHub Actions workflows to build **Nginx from source** across multiple Linux distributions, CPU architectures, and installation prefixes.

It is designed for reproducible packaging and release distribution of Nginx binaries.

---

## Features

- Builds Nginx from official source tarballs
- Supports multiple architectures:
  - `x86_64`
  - `aarch64`
- Supports multiple Linux environments:
  - CentOS 7
  - openEuler 22.03 LTS
  - Kylin V10 SP3
- Supports multiple installation prefixes:
  - `/usr/local/nginx`
  - `/opt/software/nginx`
- Includes third-party module:
  - `nginx-http-flv-module`
- Links common dependencies from source:
  - OpenSSL
  - PCRE2
  - zlib

---

## License

This repository only provides build automation scripts.
Nginx and all dependencies are subject to their respective licenses.