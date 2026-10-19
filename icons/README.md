# tbUI3-Icons

The icon library behind the Fluent UI System and Gallery tabs of tbUI3's icon picker.
Segoe Fluent Icons glyphs are not here: they come from the font Windows already has.

## Contents (2026.10.19.1)

- 21,764 Fluent UI System Icons SVGs (regular 10,267, filled 10,393, color 890, light 214),
  from [microsoft/fluentui-system-icons](https://github.com/microsoft/fluentui-system-icons)
  commit `cd332ec1f90cda2fad16f86754f8da52f1e9ab30`, MIT.
- 112 WinUI Gallery control images (PNG), from
  [microsoft/WinUI-Gallery](https://github.com/microsoft/WinUI-Gallery) `WinUIGallery/Assets/ControlImages`
  commit `05939cc7d48fc0d7288ff3c89ced86cf1a08eb9d`, MIT.

Both licences are reproduced in `NOTICE.txt` inside the zip.

## Files

- `manifest.txt` (this folder): `key=value` lines. tbUI3 reads `version`, `url`, `size` and `sha256`
  to offer an update and to check the download.
- `tbUI3-Icons-<version>.zip` (release asset): `tbUI3-Icons.dat` and `NOTICE.txt`.

## tbUI3-Icons.dat, format 1

Little-endian. Every number is a 32-bit signed integer.

| Offset | Size | Field |
| --- | --- | --- |
| 0 | 8 | ASCII `tbUI3LIB` |
| 8 | 4 | format version (1) |
| 12 | 4 | entry count |
| 16 | 4 | index offset |
| 20 | 4 | index length in bytes |
| 24 | 4 | data offset |
| 28 | 4 | data length in bytes |

The index is ASCII text with CRLF line endings. The first line is
`#tbUI3-Icons|<version>|<fluent commit>|<gallery commit>`. Each following line is one icon:

```
set|id|name|style|size|variant|tags|offset|length
F|access_time|Access Time|regular|20||number 24 Circle|0|1909
```

`set` is `F` (Fluent UI System SVG) or `G` (Gallery PNG). `id` is the file's own name, `name` is the
display name, `style` is regular, filled, color or light (empty for PNGs), `size` is the design size
in pixels, and `variant` is a locale (ar, he, ...) or ltr/rtl when the icon has one. `tags` are
space-separated. `offset` is relative to the data offset; the bytes are the original files, unchanged.
