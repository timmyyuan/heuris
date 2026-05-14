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

## Package APIs

`dupl`, `gocognit`, `prealloc`, and `unused` expose package APIs that return native Go structs and can convert to or from golangci-lint-style JSON reports.

- `dupl`: import `github.com/mibk/dupl/pkg`, then call `CheckPaths`, `CheckFiles`, or `CheckGolangCILintJSON`.
- `gocognit`: import `github.com/uudashr/gocognit`, then call `CheckPaths`, `CheckFiles`, or `CheckGolangCILintJSON`.
- `prealloc`: import `github.com/alexkohler/prealloc/pkg`, then call `CheckPackages`, `CheckPackageLines`, or `CheckPackageGolangCILintJSON`.
- `unused`: import `honnef.co/go/tools/unused`, then call `CheckPackages`, `CheckPaths`, or `CheckGolangCILintJSON`.

`dupl` and `gocognit` are syntax-only and accept file or directory paths. `prealloc` is syntax-first, accepts Go package patterns, and can optionally fall back to typechecking. `unused` accepts Go package patterns and loads type information because unused-code analysis depends on typed object identity.

All four package APIs support `ExcludePathSubstrings` in their options. Any diagnostic whose file path contains one of those configured substrings is excluded.

When using the submodules from this repository in a Go module, add local replacements so imports resolve to the checked-out rule projects:

```go
replace github.com/mibk/dupl => ./rules/go/dupl
replace github.com/uudashr/gocognit => ./rules/go/gocognit
replace github.com/alexkohler/prealloc => ./rules/go/prealloc
replace honnef.co/go/tools => ./rules/go/unused
```
