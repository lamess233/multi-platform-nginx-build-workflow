# Nginx Build Profiles

This directory contains build profile configurations for nginx compilation. Each profile defines a specific set of modules and features to include in the build.

## Available Profiles

### minimal
Basic nginx build with essential modules:
- nginx-http-flv-module (FLV/MP4 streaming)
- HTTP SSL support
- Real IP module
- Stub status module

**Use case:** Production environments requiring minimal footprint and dependencies.

### standard
Full-featured nginx build with all modules:
- All minimal modules
- HTTP/2 and HTTP/3 support
- Stream proxy modules
- Mail proxy modules
- Image/XSLT filters (dynamic)
- GeoIP modules (dynamic)
- Google perftools integration
- Debug support

**Use case:** Development, testing, or feature-rich production deployments.

## Profile File Format

Each profile is a plain text file with one configure argument per line:

```
--add-module=../nginx-http-flv-module
--with-http_ssl_module
--with-http_v2_module
```

- Blank lines and lines starting with `#` are ignored
- Each line should be a valid nginx `./configure` argument
- Arguments are appended to the base configuration

## Base Configuration

All profiles automatically include these fixed arguments:
- `--prefix` (installation path)
- `--with-openssl` (OpenSSL source)
- `--with-pcre` (PCRE2 source)
- `--with-zlib` (zlib source)
- `--with-cc-opt` (compiler flags)
- `--with-ld-opt` (linker flags)

## Usage

### In build-config.env
Set the default profile for release builds:
```bash
NGINX_BUILD_PROFILE=minimal
```

### Manual Workflow Trigger
When manually triggering the workflow, select a profile from the dropdown. Leave empty to use the value from `build-config.env`.

## Adding a New Profile

1. Create a new `.conf` file in this directory
2. Add configure arguments (one per line)
3. Update the workflow's `build_profile` input options in `.github/workflows/build-nginx-multi-distro.yml`
4. Document it in this README

Example:
```bash
# build-profiles/custom.conf
--add-module=../nginx-http-flv-module
--with-http_ssl_module
--with-http_v3_module
--with-stream=dynamic
```
