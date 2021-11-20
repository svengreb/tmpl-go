The `/apps` directory stores source code of project application(s) using the Go `main` package that can be compiled to the binary executable. It is often named `/cmd` instead, but because the name is not so appropriate and could lead to false assumptions it has been renamed for this template repository to better describe the actual content.

## Directory Structure

A common practice is that each application is placed in an individual directory that should match the name of the resulting binary executable.
The structure always depends on the type and use case(s) of the application, but in general the code only consists of the `main` package and function that mainly imports and invokes reuseable code from the [`/internal`][8] and [`/pkg`][9] directories.

Code that is only relevant for an individual application like configurations, internal logic and commands can also be placed inside directories like `config`, `internal` and `internal/cmd`. In comparison, code that is reusable and could be imported from outside the module should never be placed in the application specific directory but [`/pkg`][9].
Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the API defined in the [example of the `/api` directory][3] and additionally assuming another service application named `notes-sync` the structure for the application could be created as follows:

```raw
apps
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

Next to the experience with own projects and [golang-standards/project-layout][1], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Kubernetes][5]
- [Prometheus][7]
- [Moby][6]
- [Ardan Labs “Service Starter Kit“][2]
- [InfluxDB][4]

[1]: https://github.com/golang-standards/project-layout
[2]: https://github.com/ardanlabs/service/tree/master/app
[3]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[4]: https://github.com/influxdata/influxdb/tree/master/cmd
[5]: https://github.com/kubernetes/kubernetes/tree/master/cmd
[6]: https://github.com/moby/moby/tree/master/cmd
[7]: https://github.com/prometheus/prometheus/tree/master/cmd
[8]: https://github.com/svengreb/tmpl-go/tree/main/internal
[9]: https://github.com/svengreb/tmpl-go/tree/main/pkg
