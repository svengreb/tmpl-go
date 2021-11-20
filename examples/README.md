The `/examples` directory stores examples for provided APIs that are defined in the [`/api` directory][4], public packages from the [`/pkg` directory][6], ways to use and run applications from the [`/apps` directory][5] or to demonstrate the integration with other applications, platforms or systems.

## Directory Structure

A common practice is that each example is placed in an individual directory whose name matches its use case. Please see the [example](#example) below for a common and practical usage pattern.

## Example

Given the API defined in the [example of the `/api` directory][2] the structure could be created as follows:

```raw
examples
├─ auto-backup
└─ synchronization
```

## References

Next to the experience with own projects and [golang-standards/project-layout][1], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [NATS][3]
- [Velero][7]

[1]: https://github.com/golang-standards/project-layout
[2]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[3]: https://github.com/nats-io/nats.go/tree/master/examples
[4]: https://github.com/svengreb/tmpl-go/tree/main/api
[5]: https://github.com/svengreb/tmpl-go/tree/main/apps
[6]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[7]: https://github.com/vmware-tanzu/velero/tree/main/examples
