The `/pkg` directory stores exported (“public“) API, application and package code that, in comparison to code in the top level [`/internal`][gh-tree-internal] or any nested `internal` directory, can be imported in other modules.

One reason why this template repository make use of the top level `/pkg` directory is, next to the fact that is has already become best practice anyway, that it allows to keep the repository root clean instead of cluttering it with directories that contain Go and non-Go source code. It is also a good way to explicitly communicate that code in the `/pkg` directory is meant and safe to be used and integrated in other projects.
There are many projects with repository roots that contain more than 30 directories where you need to check each to know if it belongs to the Go code base or if it stores any other project related files. This mess is often justified only by the fact that it allows to simplify package import paths by removing the actually short `/pkg/` element, but it comes with the high price that potentially new project contributors have a significantly longer time to get used to the overall repository and code structure or even discourages them to contribute to the project at all. Therefore a simple package import path of just five additional characters is not a disadvantage at all but also comes with clear way to communicate the purpose of the code.

Note that the usage of the `/pkg` directory also always depends on the use case, so for example a really small project might not need it when the repository only contains Go code and this would only add unnecessary nesting, but most projects contain more than just Go code so a `/pkg` is often a benefit.

## Directory Structure

The layout always depends on the individual use case(s) of the project, but there are some best practices and great resources like [package naming][go-doc-eff_go#pkg_names] and [style guidelines for Go packages][blog-rakyll-stg_pkgs].

## Example

Given the [example of the `/api` directory][gh-blob-api-readme#example] the structure could be created as follows:

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

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Kubernetes][gh-kubernetes-tree-pkg]
- [Moby][gh-moby-tree-pkg]
- [etcd][gh-etcd-tree-pkg]
- [Knative][gh-knative-tree-pkg]
- [Prometheus][gh-prometheus-tree-pkg]
- [Grafana][gh-grafana-tree-pkg]
- [gVisor][gh-gvisor-tree-pkg]
- [ArgoCD][gh-argocd-tree-pkg]
- [Jaeger][gh-jaeger-tree-pkg]
- [Helm][gh-helm-tree-pkg]
- [MinIO][gh-minio-tree-pkg]

Blog posts, videos and documentations:

- [Blog Post: “I’ll take pkg over internal“][blog-travisjeffery-pkg_over_int]
- [YouTube: “GopherCon EU 2018: Peter Bourgon - Best Practices for Industrial Programming“][yt-pte4vjidhpg]
- [YouTube: “GopherCon 2018: Kat Zien - How Do You Structure Your Go Apps“][yt-ol6jbuk6tj0]

[blog-rakyll-stg_pkgs]: https://rakyll.org/style-packages
[blog-travisjeffery-pkg_over_int]: https://travisjeffery.com/b/2019/11/i-ll-take-pkg-over-internal
[gh-argocd-tree-pkg]: https://github.com/argoproj/argo-cd/tree/master/pkg
[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-etcd-tree-pkg]: https://github.com/etcd-io/etcd/tree/master/pkg
[gh-grafana-tree-pkg]: https://github.com/grafana/grafana/tree/master/pkg
[gh-gvisor-tree-pkg]: https://github.com/google/gvisor/tree/master/pkg
[gh-helm-tree-pkg]: https://github.com/helm/helm/tree/master/pkg
[gh-jaeger-tree-pkg]: https://github.com/jaegertracing/jaeger/tree/master/pkg
[gh-knative-tree-pkg]: https://github.com/knative/serving/tree/master/pkg
[gh-kubernetes-tree-pkg]: https://github.com/kubernetes/kubernetes/tree/master/pkg
[gh-minio-tree-pkg]: https://github.com/minio/minio/tree/master/pkg
[gh-moby-tree-pkg]: https://github.com/moby/moby/tree/master/pkg
[gh-prometheus-tree-pkg]: https://github.com/prometheus/prometheus/tree/master/pkg
[gh-tree-internal]: https://github.com/svengreb/tmpl-go/tree/main/internal
[go-doc-eff_go#pkg_names]: https://golang.org/doc/effective_go.html#package-names
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
[yt-ol6jbuk6tj0]: https://www.youtube.com/watch?v=oL6JBUk6tj0
[yt-pte4vjidhpg]: https://www.youtube.com/watch?v=PTE4VJIdHPg
