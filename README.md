# libghostty-spm

libghostty-spm is Ignis Labs' Ghostty terminal surface package for Apple platforms.

It vendors the Swift `GhosttyTerminal` wrapper from `Lakr233/libghostty-spm` and pins the matching prebuilt `GhosttyKit.xcframework` artifact locally so app builds do not depend on Xcode downloading a binary target during project generation.

## Products

- `GhosttyKit`: thin Swift module that re-exports the vendored `libghostty` C module.
- `GhosttyTerminal`: UIKit and SwiftUI terminal surface backed by libghostty, including in-memory host-managed input and output.

## Casper Integration

Casper should depend on this package and link the `GhosttyTerminal` product. The app owns session/bookmark state and host transport; this package owns terminal rendering, input translation, and VT state.

## Upstream

Source wrapper and artifact lineage:

- `Lakr233/libghostty-spm`
- `ghostty-org/ghostty`

The full embedded libghostty API is still not a stable public upstream API, so keep Casper’s usage behind a narrow app-side boundary.
