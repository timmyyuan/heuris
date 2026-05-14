# Go Rules

This directory contains Go static-analysis heuristic projects.

## Submodules

- [`dupl`](dupl/) detects duplicated Go code.
- [`gocognit`](gocognit/) calculates cognitive complexity for Go functions and methods.
- [`prealloc`](prealloc/) checks Go slice declarations that are followed by predictable appends and can benefit from explicit capacity.
- [`unused`](unused/) mirrors `dominikh/go-tools`; the analyzer package used by golangci-lint lives in [`unused/unused`](unused/unused/).

## Sources

- `dupl`: [`mibk/dupl`](https://github.com/mibk/dupl) mirrored to [`timmyyuan/dupl`](https://github.com/timmyyuan/dupl)
- `gocognit`: [`uudashr/gocognit`](https://github.com/uudashr/gocognit) mirrored to [`timmyyuan/gocognit`](https://github.com/timmyyuan/gocognit)
- `prealloc`: [`timmyyuan/prealloc`](https://github.com/timmyyuan/prealloc)
- `unused`: [`dominikh/go-tools/unused`](https://github.com/dominikh/go-tools/tree/HEAD/unused) kept with its full `go-tools` repository context in [`timmyyuan/unused`](https://github.com/timmyyuan/unused)
