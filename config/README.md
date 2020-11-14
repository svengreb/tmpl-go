The `/config` directory, also often named `contrib`, stores all configurations of any kind such as…

- …container orchestration deployments — tools like Automated scaling and management systems like [Kubernetes][] or [Docker Compose][docker-compose] as well as tools to manage and process their configurations like [Kustomize][] and [Helm][].
- …application configuration templates — reference, example or starter files that contain default values configurations of applications in the [`/apps` directory][gh-tree-apps].
- …platform and distribution specific configurations — basic, platform specific configuration files for distribution or deployment purposes like for example [systemd][] units, process managers/supervisors or reverse proxies.

## Directory Structure

The files should be placed in separate directories based on their purpose or target technology. Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the [example of the `/api` directory][gh-blob-api-readme#example] the structure for some common configurations could be created as follows:

```raw
config
├─ apps
│  └─ notes
├─ deployment
│  ├─ docker
│  │  └─ compose
│  └─ k8s
│     ├─ base
│     ├─ local
│     ├─ development
│     └─ production
├─ packaging
│  ├─ linux
│  │  ├─ arch
│  │  ├─ deb
│  │  └─ flatpak
│  └─ macos
│     ├─ homebrew
│     └─ pkg
├─ platform
│  ├─ nomad
│  └─ systemd
└─ security
   ├─ certs
   └─ secrets
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Moby][gh-moby-tree-contrib]
- [Knative][gh-knative-tree-config]
- [Ardan Labs “Service Starter Kit“][gh-ardanlabs/service-tree-zarf]
- [Loki][gh-loki-tree-production]
- [NATS][gh-nats-server-tree-docker]
- [etcd][gh-etcd-tree-contrib]
- Dapr ([Helm Charts][gh-dapr-tree-charts], [Grafana][gh-dapr-tree-grafana], [Docker][gh-dapr-tree-docker], [Swagger][gh-dapr-tree-swagger])
- [Velero][gh-velero-tree-config]
- [Kubernetes][gh-kubernetes-tree-hack]

[docker-compose]: https://docs.docker.com/compose
[gh-ardanlabs/service-tree-zarf]: https://github.com/ardanlabs/service/tree/master/zarf
[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-dapr-tree-charts]: https://github.com/dapr/dapr/tree/master/charts/dapr
[gh-dapr-tree-docker]: https://github.com/dapr/dapr/tree/master/docker
[gh-dapr-tree-grafana]: https://github.com/dapr/dapr/tree/master/grafana
[gh-dapr-tree-swagger]: https://github.com/dapr/dapr/tree/master/swagger
[gh-etcd-tree-contrib]: https://github.com/etcd-io/etcd/tree/master/contrib
[gh-knative-tree-config]: https://github.com/knative/serving/tree/master/config
[gh-kubernetes-tree-hack]: https://github.com/kubernetes/kubernetes/tree/master/hack
[gh-loki-tree-production]: https://github.com/grafana/loki/tree/master/production
[gh-moby-tree-contrib]: https://github.com/moby/moby/tree/master/contrib
[gh-nats-server-tree-docker]: https://github.com/nats-io/nats-server/tree/master/docker
[gh-tree-apps]: https://github.com/svengreb/tmpl-go/tree/main/apps
[gh-velero-tree-config]: https://github.com/vmware-tanzu/velero/tree/main/config
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
[helm]: https://helm.sh
[kubernetes]: https://kubernetes.io
[kustomize]: https://kustomize.io
[systemd]: https://www.freedesktop.org/wiki/Software/systemd
