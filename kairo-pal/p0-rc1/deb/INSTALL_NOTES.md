# KAIRO+PAL P0 RC1 corrected accel-vulkan artifact

This RC1 artifact replaces the earlier unpublished RC1 package whose build path omitted `--features accel-vulkan`.

The replacement is made before public RC1 announcement.

## Validation status

- Extracted package validation: PASS
- `kairo-aegis status`: PASS
- `kairo-aegis smoke`: PASS
- `kairo-aegis vulkan-selftest`: PASS
- `vulkan_feature_enabled=true`: confirmed
- `vulkan_runtime_available=true`: confirmed
- Vulkan dispatch: confirmed
- SIGSEGV: not reproduced

## Notes

The previous Debian/Ubuntu/Fedora RC1 validation evidence remains useful for service and multi-OS behavior, but it was based on a package where Vulkan was not enabled in the distributed binary. This corrected RC1 must be re-run through host install validation and the QEMU OS matrix before public release.
