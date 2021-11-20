The `/config` directory, also often named `contrib`, stores all configurations of any kind such as…

- …container orchestration deployments — tools like Automated scaling and management systems like [Kubernetes][1] or [Docker Compose][4] as well as tools to manage and process their configurations like [Kustomize][3] and [Helm][2].
- …application configuration templates — reference, example or starter files that contain default values configurations of applications in the [`/apps` directory][19].
- …platform and distribution specific configurations — basic, platform specific configuration files for distribution or deployment purposes like for example [systemd][5] units, process managers/supervisors or reverse proxies.

## Directory Structure

The files should be placed in separate directories based on their purpose or target technology. Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the [example of the `/api` directory][8] the structure for some common configurations could be created as follows:

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

Next to the experience with own projects and [golang-standards/project-layout][6], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Moby][17]
- [Knative][14]
- [Ardan Labs “Service Starter Kit“][7]
- [Loki][16]
- [NATS][18]
- [etcd][13]
- Dapr ([Helm Charts][9], [Grafana][11], [Docker][10], [Swagger][12])
- [Velero][20]
- [Kubernetes][15]

[1]: https://kubernetes.io
[2]: https://helm.sh
[3]: https://kustomize.io
[4]: https://docs.docker.com/compose
[5]: https://www.freedesktop.org/wiki/Software/systemd
[6]: https://github.com/golang-standards/project-layout
[7]: https://github.com/ardanlabs/service/tree/master/zarf
[8]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[9]: https://github.com/dapr/dapr/tree/master/charts/dapr
[10]: https://github.com/dapr/dapr/tree/master/docker
[11]: https://github.com/dapr/dapr/tree/master/grafana
[12]: https://github.com/dapr/dapr/tree/master/swagger
[13]: https://github.com/etcd-io/etcd/tree/master/contrib
[14]: https://github.com/knative/serving/tree/master/config
[15]: https://github.com/kubernetes/kubernetes/tree/master/hack
[16]: https://github.com/grafana/loki/tree/master/production
[17]: https://github.com/moby/moby/tree/master/contrib
[18]: https://github.com/nats-io/nats-server/tree/master/docker
[19]: https://github.com/svengreb/tmpl-go/tree/main/apps
[20]: https://github.com/vmware-tanzu/velero/tree/main/config
