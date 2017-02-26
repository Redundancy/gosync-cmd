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

{{cli "./gosync-cmd" "-h"}}
{{cli "./gosync-cmd" "build" "-h"}}
{{cli "./gosync-cmd" "diff" "-h"}}
{{cli "./gosync-cmd" "patch" "-h"}}

## Cli examples

???
