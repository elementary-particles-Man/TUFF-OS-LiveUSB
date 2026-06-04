# KAIRO+PAL P0 RC1 Debian package

Status: pre-QEMU-integration-test.

This RC1 artifact adds `/usr/libexec/kairo-pal-daemon` to the RC0 KAIRO+PAL package scaffold.

The daemon is built from TUFF-PAL/core and is init-system-neutral. It emits JSON-lines to stdout/stderr and performs no network access, no enforcement actions, and no OS mutation.

The Debian package includes a systemd unit for Debian-host validation, but systemd integration is packaging-side only and is not a TUFF-PAL runtime dependency.

This artifact is not latest, stable, or production-ready.

Validation performed before staging:

- daemon built in release mode
- extracted daemon executed with `--once`
- package contents inspected with `dpkg-deb -I` and `dpkg-deb -c`
- `/usr/libexec/kairo-pal-daemon` confirmed present and executable
- no package install was performed
- no service start was performed
- no QEMU run was performed

Next steps:

1. Install RC1 on the host test PC.
2. Validate `kairo-pal.service` manual start.
3. Build QEMU multi-OS test environments.
