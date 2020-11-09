The `/app` directory stores source code of project application(s) using the Go `main` package that can be compiled to the binary executable. It is often named `/cmd` instead, but because the name is not so appropriate and could lead to false assumptions it has been renamed for this template repository to better describe the actual content.

## Directory Structure

A common practice is that each application is placed in an individual directory that should match the name of the resulting binary executable.
The structure always depends on the type and use case(s) of the application, but in general the code only consists of the `main` package and function that mainly imports and invokes reuseable code from the [`/internal`][gh-tree-internal] and [`/pkg`][gh-tree-pkg] directories.

Code that is only relevant for an individual application like configurations, internal logic and commands can also be placed inside directories like `config`, `internal` and `internal/cmd`. In comparison, code that is reusable and could be imported from outside the module should never be placed in the application specific directory but [`/pkg`][gh-tree-pkg].
Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the API defined in the [example of the `/api` directory][gh-blob-api-readme#example] and additionally assuming another service application named `notes-sync` the structure for the application could be created as follows:

```raw
app
├─ notes
│  ├─ config
│  └─ internal
│     └─ cmd
│        ├─ archive
│        ├─ create
│        └─ delete
└─ notes-sync
    ├─ config
    └─ internal
        └─ cmd
           ├─ export
           └─ serve
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Kubernetes][gh-kubernetes-tree-cmd]
- [Prometheus][gh-prometheus-tree-cmd]
- [Moby][gh-moby-tree-cmd]
- [Ardan Labs “Service Starter Kit“][ardanlabs/service]
- [InfluxDB][gh-influxdb-tree-cmd]

[ardanlabs/service]: https://github.com/ardanlabs/service/tree/master/app
[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-influxdb-tree-cmd]: https://github.com/influxdata/influxdb/tree/master/cmd
[gh-kubernetes-tree-cmd]: https://github.com/kubernetes/kubernetes/tree/master/cmd
[gh-moby-tree-cmd]: https://github.com/moby/moby/tree/master/cmd
[gh-prometheus-tree-cmd]: https://github.com/prometheus/prometheus/tree/master/cmd
[gh-tree-internal]: https://github.com/svengreb/tmpl-go/tree/main/internal
[gh-tree-pkg]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
