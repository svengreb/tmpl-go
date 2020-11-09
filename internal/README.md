The `/internal` directory stores non-exported (“private“) application and package code that, in comparison to code in the [`/pkg` directory][gh-tree-pkg], can never be imported in other modules. As of [Go version 1.4 the compiler itself enforces the `internal` directory naming pattern][go-doc-rln-1.4#int_pkg] and prevents all packages within this directory to be imported by other modules outside the module in which they reside. Note that this pattern it not limited to the top level `/internal` directory but to any nested `internal` directory within the module.

## Directory Structure

A common practice is that the `/internal` directory contains sub-directories to separate code targeted only for individual applications using the same pattern like the [`/app` directory][gh-tree-pkg] or module-wide code like stored in the [`/pkg` directory][gh-tree-pkg].

each application is placed in an individual directory that should match the name of the resulting binary executable.
The structure always depends on the type and use case(s) of the application, but in general the code only consists of the `main` package and function that mainly imports and invokes reuseable code from the [`/internal`][gh-tree-internal] and directories. This helps to better visualize the intended package use and distinguish shared and non-shared code.

## Example

Given the [example of the `/api` directory][gh-blob-api-readme#example] the structure could be created as follows:

```raw
internal
├─ app
│  ├─ notes
│  └─ notes-sync
└─ pkg
   ├─ platform
   │  ├─ http
   │  ├─ logging
   │  ├─ messaging
   │  └─ transport
   ├─ product
   │  └─ store
   └─ support
      ├─ data
      └─ project
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Terraform][gh-terraform-tree-internal]
- [NATS][gh-nats-server-tree-internal]
- [InfluxDB][gh-influxdb-tree-internal]
- [Perkeep][gh-perkeep-tree-internal]
- [Jaeger][gh-jaeger-tree-internal]
- [Waypoint][gh-waypoint-tree-internal-pkg]

[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-influxdb-tree-internal]: https://github.com/influxdata/influxdb/tree/master/internal
[gh-jaeger-tree-internal]: https://github.com/jaegertracing/jaeger/tree/master/internal
[gh-nats-server-tree-internal]: https://github.com/nats-io/nats-server/tree/master/internal
[gh-perkeep-tree-internal]: https://github.com/perkeep/perkeep/tree/master/internal
[gh-terraform-tree-internal]: https://github.com/hashicorp/terraform/tree/master/internal
[gh-tree-internal]: https://github.com/svengreb/tmpl-go/tree/main/internal
[gh-tree-pkg]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[gh-waypoint-tree-internal-pkg]: https://github.com/hashicorp/waypoint/tree/main/internal/pkg
[go-doc-rln-1.4#int_pkg]: https://golang.org/doc/go1.4#internalpackages
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
