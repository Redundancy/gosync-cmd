# {{.Name}}

{{template "badge/travis" .}}{{template "badge/appveyor" .}}{{template "badge/godoc" .}}

{{pkgdoc}}

This forks the CLI code that was originally in https://github.com/Redundancy/go-sync
In order to separate the library from the tool, and to bring proper vendoring to the tool.

# Install

### Glide

{{template "glide/install" .}}

### run/build

```sh
go run *.go
go build -o gosync-cmd *.go
emd gen -out README.md
```

# Usage

{{cli "./go-sync" "-h"}}
{{cli "./go-sync" "build" "-h"}}
{{cli "./go-sync" "diff" "-h"}}
{{cli "./go-sync" "patch" "-h"}}

## Cli examples

???
