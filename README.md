# tbUI3-Libraries

Optional design-time libraries for [tbUI3](https://github.com/Arrow-Loop/tbUI3), the twinBASIC
package of WinUI 3 style controls. The tbUI3 property pages install, update, reinstall and
uninstall them for you; you never need to download anything from here by hand.

A library lives on the developer's PC only (under `%LOCALAPPDATA%\tbUI3`). Built apps carry
only the items a developer picked, copied into the control's saved properties.

| Library | Folder | What it holds |
| --- | --- | --- |
| tbUI3-Icons | [icons](icons) | Fluent UI System Icons (SVG) and the WinUI Gallery control images (PNG) |

Each library has a `manifest.txt` on `main` describing its current release. The release
itself is a zip attached to a GitHub release tagged `<library>-<version>`, for example
`icons-2026.10.19.1`.
