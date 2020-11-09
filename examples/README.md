The `/examples` directory stores examples for provided APIs that are defined in the [`/api` directory][gh-tree-api], public packages from the [`/pkg` directory][gh-tree-pkg], ways to use and run applications from the [`/app` directory][gh-tree-app] or to demonstrate the integration with other applications, platforms or systems.

## Directory Structure

A common practice is that each example is placed in an individual directory whose name matches its use case. Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the API defined in the [example of the `/api` directory][gh-blob-api-readme#example] the structure could be created as follows:

```raw
examples
├─ auto-backup
└─ synchronization
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [NATS][gh-nats-tree-examples]
- [Velero][gh-velero-tree-examples]

[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-nats-tree-examples]: https://github.com/nats-io/nats.go/tree/master/examples
[gh-tree-api]: https://github.com/svengreb/tmpl-go/tree/main/api
[gh-tree-app]: https://github.com/svengreb/tmpl-go/tree/main/app
[gh-tree-pkg]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[gh-velero-tree-examples]: https://github.com/vmware-tanzu/velero/tree/main/examples
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
