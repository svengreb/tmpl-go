The `/docs` directory stores project documentations, [runbooks][24] and any other kind of textual reference. These are often written in formats like [Markdown][23] and, depending on the project scope and technology stack, require a preprocessor. Note that documentations built with web based tools like [static site generators][22] (e.g. [Gatsby][1], [Next.js][3] or [Hugo][2]) should be placed as own package in the [`/web` directory][19].

## Directory Structure

The layout always depends on the individual use case(s) of the project and when hosted on platforms like [GitHub Pages][8] or [GitLab Pages][21]. A common practice is to store documentations in separate repositories, often in combination with static site generator configurations, for example the [official Kubernetes website][14] or [Knative documentations][13].

## Example

Given the [example of the `/api` directory][6] the structure for some common configurations could be created as follows:

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

Next to the experience with own projects and [golang-standards/project-layout][4], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Dapr][7]
- [Perkeep][17]
- [Hugo][11]
- [Argo][5]
- [Prometheus][18]
- [Moby][16]
- [Knative][12]
- [MinIO][15]
- [GoPass][10]
- [Flynn][9]
- [Flynn][9]
- [Velero][20]

[1]: https://www.gatsbyjs.com
[2]: https://gohugo.io
[3]: https://jamstack.org/generators/next
[4]: https://github.com/golang-standards/project-layout
[5]: https://github.com/argoproj/argo/tree/master/docs
[6]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[7]: https://github.com/dapr/dapr/tree/master/docs
[8]: https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/about-github-pages
[9]: https://github.com/flynn/flynn/tree/master/docs
[10]: https://github.com/gopasspw/gopass/tree/master/docs
[11]: https://github.com/gohugoio/hugo/tree/master/docs
[12]: https://github.com/knative/serving/tree/master/docs
[13]: https://github.com/knative/docs
[14]: https://github.com/kubernetes/website
[15]: https://github.com/minio/minio/tree/master/docs
[16]: https://github.com/moby/moby/tree/master/docs
[17]: https://github.com/perkeep/perkeep/tree/master/doc
[18]: https://github.com/prometheus/prometheus/tree/master/docs
[19]: https://github.com/svengreb/tmpl-go/tree/main/web
[20]: https://github.com/vmware-tanzu/velero/tree/main/design
[21]: https://about.gitlab.com/stages-devops-lifecycle/pages
[22]: https://jamstack.org/generators
[23]: https://en.wikipedia.org/wiki/Markdown
[24]: https://en.wikipedia.org/wiki/Runbook
