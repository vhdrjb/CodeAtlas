# Migration Guide

This guide covers upgrading between versions of Code Atlas. Code Atlas uses semantic versioning (MAJOR.MINOR.PATCH).

---

## Version 1.0.0

This is the initial release. There is no migration from a previous version.

---

## Future Migration Notes

### Adding New Modes

When a new mode is added in a minor version, it will not change any existing behavior. Existing configurations continue to work identically. To use the new mode, specify it in your prompt.

### Adding New Audiences

New audiences follow the same non-breaking pattern. Existing outputs are unaffected.

### Template Changes

Template changes in minor versions will be additive (new optional sections). Required sections will not be removed or renamed in minor versions. Major versions may restructure templates.

### Knowledge Model Changes

The knowledge model schema may receive new fields in minor versions. These fields are optional — existing analyses that do not populate them will continue to work. Major versions may restructure the schema.

### Deprecation Policy

- Features deprecated in version N.X will be removed in version (N+1).0.
- Deprecated features will produce a warning in the output.
- Migration instructions will be provided in the release notes.

---

## Backwards Compatibility

Code Atlas is designed for maximum backwards compatibility:

- All configuration files use a simple Markdown format that is easy to diff and merge.
- New dimensions (modes, audiences, purposes) are additive.
- The knowledge model schema is extended, not modified.
- Templates add optional sections rather than restructuring.

---

## Custom Extensions and Upgrades

If you have created custom extensions (modes, audiences, purposes, templates), they will continue to work after upgrading Code Atlas because:

1. Extensions are separate files that are not modified during upgrades.
2. The core skill definition does not reference specific dimension files by name (except in the default mapping table).
3. Custom dimensions compose with upstream dimensions using the same mechanism.

The only scenario where a custom extension might need updating is if the knowledge model schema changes in a way that removes or renames a field your extension references. This would only occur in a major version and would be documented in the release notes.
