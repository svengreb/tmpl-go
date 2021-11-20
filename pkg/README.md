The `/pkg` directory stores exported (“public“) API, application and package code that, in comparison to code in the top level [`/internal`][16] or any nested `internal` directory, can be imported in other modules.

One reason why this template repository make use of the top level `/pkg` directory is, next to the fact that is has already become best practice anyway, that it allows to keep the repository root clean instead of cluttering it with directories that contain Go and non-Go source code. It is also a good way to explicitly communicate that code in the `/pkg` directory is meant and safe to be used and integrated in other projects.
There are many projects with repository roots that contain more than 30 directories where you need to check each to know if it belongs to the Go code base or if it stores any other project related files. This mess is often justified only by the fact that it allows to simplify package import paths by removing the actually short `/pkg/` element, but it comes with the high price that potentially new project contributors have a significantly longer time to get used to the overall repository and code structure or even discourages them to contribute to the project at all. Therefore a simple package import path of just five additional characters is not a disadvantage at all but also comes with clear way to communicate the purpose of the code.

Note that the usage of the `/pkg` directory also always depends on the use case, so for example a really small project might not need it when the repository only contains Go code and this would only add unnecessary nesting, but most projects contain more than just Go code so a `/pkg` is often a benefit.

## Directory Structure

The layout always depends on the individual use case(s) of the project, but there are some best practices and great resources like [package naming][17] and [style guidelines for Go packages][2].

## Example

Given the [example of the `/api` directory][5] the structure could be created as follows:

```raw
pkg
├─ api
│  └─ v1
│     └─ notes
│        └─ states
├─ data
│  ├─ source
│  │  └─ file
│  └─ encoder
│     └─ yaml
└─ parser
    ├─ config
    └─ events
        └─ handler
```

## References

Next to the experience with own projects and [golang-standards/project-layout][1], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Kubernetes][12]
- [Moby][14]
- [etcd][6]
- [Knative][11]
- [Prometheus][15]
- [Grafana][7]
- [gVisor][8]
- [ArgoCD][4]
- [Jaeger][10]
- [Helm][9]
- [MinIO][13]

Blog posts, videos and documentations:

- [Blog Post: “I’ll take pkg over internal“][3]
- [YouTube: “GopherCon EU 2018: Peter Bourgon - Best Practices for Industrial Programming“][19]
- [YouTube: “GopherCon 2018: Kat Zien - How Do You Structure Your Go Apps“][18]

[1]: https://github.com/golang-standards/project-layout
[2]: https://rakyll.org/style-packages
[3]: https://travisjeffery.com/b/2019/11/i-ll-take-pkg-over-internal
[4]: https://github.com/argoproj/argo-cd/tree/master/pkg
[5]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[6]: https://github.com/etcd-io/etcd/tree/master/pkg
[7]: https://github.com/grafana/grafana/tree/master/pkg
[8]: https://github.com/google/gvisor/tree/master/pkg
[9]: https://github.com/helm/helm/tree/master/pkg
[10]: https://github.com/jaegertracing/jaeger/tree/master/pkg
[11]: https://github.com/knative/serving/tree/master/pkg
[12]: https://github.com/kubernetes/kubernetes/tree/master/pkg
[13]: https://github.com/minio/minio/tree/master/pkg
[14]: https://github.com/moby/moby/tree/master/pkg
[15]: https://github.com/prometheus/prometheus/tree/master/pkg
[16]: https://github.com/svengreb/tmpl-go/tree/main/internal
[17]: https://golang.org/doc/effective_go.html#package-names
[18]: https://www.youtube.com/watch?v=oL6JBUk6tj0
[19]: https://www.youtube.com/watch?v=PTE4VJIdHPg
