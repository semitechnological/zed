# TODO

## Crepuscularity GPUI Migration

- Keep `crepuscularity-gpui` backed by online `gpui = "=0.2.2"`; do not use Zed-local or vendored GPUI as the backend.
- Continue growing `crepuscularity-gpui` as the compatibility facade for public Zed GPUI surface gaps.
- `cargo check -p ui` currently passes with warnings against the online-GPUI-backed facade.
- `cargo check -p zed` is blocked at local `crates/gpui_macos`, which depends on Zed-local GPUI internals that online `gpui 0.2.2` does not expose.
- Resolve the `gpui_macos` boundary by replacing/disabling local platform internals or using an online-compatible platform backend.
- After the platform boundary is resolved, continue the compile-error-driven migration upward from `cargo check -p zed`.
