The `/docs` directory stores project documentations, [runbooks][wikip-runbook] and any other kind of textual reference. These are often written in formats like [Markdown][wikip-md] and, depending on the project scope and technology stack, require a preprocessor. Note that documentations built with web based tools like [static site generators][jamstack-gens] (e.g. [Gatsby][], [Next.js][] or [Hugo][]) should be placed as own package in the [`/web` directory][gh-tree-web].

## Directory Structure

The layout always depends on the individual use case(s) of the project and when hosted on platforms like [GitHub Pages][gh-docs-pages] or [GitLab Pages][gl-pages]. A common practice is to store documentations in separate repositories, often in combination with static site generator configurations, for example the [official Kubernetes website][gh-kubernetes/website] or [Knative documentations][gh-knative/docs].

## Example

Given the [example of the `/api` directory][gh-blob-api-readme#example] the structure for some common configurations could be created as follows:

```raw
docs
└─ notes
   ├─ adr
   │  ├─ api
   │  ├─ architecture
   │  ├─ cli
   │  ├─ engineering
   │  ├─ sdk
   │  └─ specification
   ├─ api
   ├─ guides
   │  ├─ development
   │  ├─ roadmap
   │  └─ runbook
   └─ maintenance
      ├─ release
      │  └─ notes
      ├─ runbook
      └─ support
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Dapr][gh-dapr-tree-docs]
- [Perkeep][gh-perkeep-tree-doc]
- [Hugo][gh-hugo-tree-docs]
- [Argo][gh-argo-tree-docs]
- [Prometheus][gh-prometheus-tree-docs]
- [Moby][gh-moby-tree-docs]
- [Knative][gh-knative-tree-docs]
- [MinIO][gh-minio-tree-docs]
- [GoPass][gh-gopass-tree-docs]
- [Flynn][gh-flynn-tree-docs]
- [Flynn][gh-flynn-tree-docs]
- [Velero][gh-velero-tree-design]

[gatsby]: https://www.gatsbyjs.com
[gh-argo-tree-docs]: https://github.com/argoproj/argo/tree/master/docs
[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-dapr-tree-docs]: https://github.com/dapr/dapr/tree/master/docs
[gh-docs-pages]: https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/about-github-pages
[gh-flynn-tree-docs]: https://github.com/flynn/flynn/tree/master/docs
[gh-gopass-tree-docs]: https://github.com/gopasspw/gopass/tree/master/docs
[gh-hugo-tree-docs]: https://github.com/gohugoio/hugo/tree/master/docs
[gh-knative-tree-docs]: https://github.com/knative/serving/tree/master/docs
[gh-knative/docs]: https://github.com/knative/docs
[gh-kubernetes/website]: https://github.com/kubernetes/website
[gh-minio-tree-docs]: https://github.com/minio/minio/tree/master/docs
[gh-moby-tree-docs]: https://github.com/moby/moby/tree/master/docs
[gh-perkeep-tree-doc]: https://github.com/perkeep/perkeep/tree/master/doc
[gh-prometheus-tree-docs]: https://github.com/prometheus/prometheus/tree/master/docs
[gh-tree-web]: https://github.com/svengreb/tmpl-go/tree/main/web
[gh-velero-tree-design]: https://github.com/vmware-tanzu/velero/tree/main/design
[gl-pages]: https://about.gitlab.com/stages-devops-lifecycle/pages
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
[hugo]: https://gohugo.io
[jamstack-gens]: https://jamstack.org/generators
[next.js]: https://jamstack.org/generators/next
[wikip-md]: https://en.wikipedia.org/wiki/Markdown
[wikip-runbook]: https://en.wikipedia.org/wiki/Runbook
