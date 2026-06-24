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

## Download

```Shell
# Set your platform variables (adjust as needed)
VERSION=1.31.2
ARCH=x86_64 # x86_64/aarch64
PLATFORM=openeuler_22_03 # openeuler_22_03 / openeuler_24_03 / kylin_v10
PRIFIX=usr_local  # usr_local / opt_software

wget https://github.com/lamess233/multi-platform-nginx-build-workflow/releases/download/${VERSION}/nginx-${VERSION}-${ARCH}-${PLATFORM}-${PRIFIX}.tar.gz
```

---

## License

This repository only provides build automation scripts.
Nginx and all dependencies are subject to their respective licenses.