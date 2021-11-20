The `/internal` directory stores non-exported (“private“) application and package code that, in comparison to code in the [`/pkg` directory][10], can never be imported in other modules. As of [Go version 1.4 the compiler itself enforces the `internal` directory naming pattern][12] and prevents all packages within this directory to be imported by other modules outside the module in which they reside. Note that this pattern it not limited to the top level `/internal` directory but to any nested `internal` directory within the module.

## Directory Structure

A common practice is that the `/internal` directory contains sub-directories to separate code targeted only for individual applications using the same pattern like the [`/apps` directory][9] or module-wide code like stored in the [`/pkg` directory][10].

Each application is placed in an individual directory that should match the name of the resulting binary executable.
The structure always depends on the type and use case(s) of the application, but in general the code only consists of the `main` package and function that mainly imports and invokes reuseable code from the [`/internal`][8] and directories. This helps to better visualize the intended package use and distinguish shared and non-shared code.

## Example

Given the [example of the `/api` directory][2] the structure could be created as follows:

```raw
internal
├─ apps
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

Next to the experience with own projects and [golang-standards/project-layout][1], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Terraform][7]
- [NATS][5]
- [InfluxDB][3]
- [Perkeep][6]
- [Jaeger][4]
- [Waypoint][11]

[1]: https://github.com/golang-standards/project-layout
[2]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[3]: https://github.com/influxdata/influxdb/tree/master/internal
[4]: https://github.com/jaegertracing/jaeger/tree/master/internal
[5]: https://github.com/nats-io/nats-server/tree/master/internal
[6]: https://github.com/perkeep/perkeep/tree/master/internal
[7]: https://github.com/hashicorp/terraform/tree/master/internal
[8]: https://github.com/svengreb/tmpl-go/tree/main/internal
[9]: https://github.com/svengreb/tmpl-go/tree/main/apps
[10]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[11]: https://github.com/hashicorp/waypoint/tree/main/internal/pkg
[12]: https://golang.org/doc/go1.4#internalpackages
