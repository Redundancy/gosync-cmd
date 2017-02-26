# gosync-cmd

[![travis Status](https://travis-ci.org/mh-cbon/gosync-cmd.svg?branch=master)](https://travis-ci.org/mh-cbon/gosync-cmd)[![appveyor Status](https://ci.appveyor.com/api/projects/status/github/mh-cbon/gosync-cmd?branch=master&svg=true)](https://ci.appveyor.com/project/mh-cbon/gosync-cmd)
[![GoDoc](https://godoc.org/github.com/mh-cbon/gosync-cmd?status.svg)](http://godoc.org/github.com/mh-cbon/gosync-cmd)


Package gosync-cmd is a command-line implementation
of the gosync package functionality,
primarily as a demonstration of usage
but supposed to be functional in itself.


This forks the CLI code that was originally in https://github.com/Redundancy/go-sync
In order to separate the library from the tool, and to bring proper vendoring to the tool.

# Install

### Glide


```sh
mkdir -p $GOPATH/src/github.com/mh-cbon/gosync-cmd
cd $GOPATH/src/github.com/mh-cbon/gosync-cmd
git clone https://github.com/mh-cbon/gosync-cmd.git .
glide install
go install
```


### run/build

```sh
go run *.go
go build -o gosync-cmd *.go
emd gen -out README.md
```

# Usage


__$ gosync-cmd -h__
```sh
NAME:
   gosync - Build indexes, patches, patch files

USAGE:
   gosync-cmd [global options] command [command options] [arguments...]

VERSION:
   0.2.1

COMMANDS:
     build, b  build a .gosync file for a file
     diff, d   gosync diff <localfile> <reference.gosync>
     patch, p  gosync patch <localfile> <reference index> <reference source> [<output>]
     help, h   Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --profile            enable HTTP profiling
   --profilePort value  The number of streams to use concurrently (default: 6060)
   --help, -h           show help
   --version, -v        print the version
```

__$ gosync-cmd build -h__
```sh
NAME:
   gosync-cmd build - build a .gosync file for a file

USAGE:
   gosync-cmd build [command options] [arguments...]

OPTIONS:
   --blocksize value  The block size to use for the gosync file (default: 8192)
```

__$ gosync-cmd diff -h__
```sh
NAME:
   gosync-cmd diff - gosync diff <localfile> <reference.gosync>

USAGE:
   gosync-cmd diff [command options] [arguments...]

DESCRIPTION:
   Compare a file with a reference index, and print statistics on the comparison and performance.

OPTIONS:
   -p value  The number of streams to use concurrently (default: 4)
```

__$ gosync-cmd patch -h__
```sh
NAME:
   gosync-cmd patch - gosync patch <localfile> <reference index> <reference source> [<output>]

USAGE:
   gosync-cmd patch [command options] [arguments...]

DESCRIPTION:
   Recreate the reference source file, using an index and a local file that is believed to be similar.
The index should be produced by "gosync build".

<reference index> is a .gosync file and may be a local, unc network path or http/https url
<reference source> is corresponding target and may be a local, unc network path or http/https url
<output> is optional. If not specified, the local file will be overwritten when done.

OPTIONS:
   -p value  The number of streams to use concurrently (default: 4)
```

## Cli examples

???
