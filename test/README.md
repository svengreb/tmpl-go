The `/test` directory, also often named `spec`, stores additional data and tools for automated testing.

Additional external test applications and test data. Feel free to structure the /test directory anyway you want. For bigger projects it makes sense to have a data subdirectory. For example, you can have /test/data or /test/testdata if you need Go to ignore what's in that directory. Note that Go will also ignore directories or files that begin with "." or "\_", so you have more flexibility in terms of how you name your test data directory.

## Directory Structure

The layout always depends on the individual use case(s) of the project, but there are resources like the official documentations of the [`go test` command][10], which includes information about directories named `testdata`, and about [package lists and patterns][9].

## Example

```raw
test
├─ conformance
│  └─ testdata
├─ e2e
│  └─ testdata
├─ fixtures
│  └─ testdata
├─ functional
│  └─ testdata
├─ fuzzing
│  └─ testdata
├─ integration
│  └─ testdata
├─ migration
│  └─ testdata
├─ performance
│  └─ testdata
├─ specifications
└─ utils
   └─ config
```

## References

Next to the experience with own projects and [golang-standards/project-layout][1], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Knative][7]
- [Kubernetes][8]
- [etcd][4]
- [Argo][3]
- [Helm][6]
- [GoPass][5]

Blog posts, videos and documentations:

- [Blog Post: “Test fixtures in Go“][2]

[1]: https://github.com/golang-standards/project-layout
[2]: https://dave.cheney.net/2016/05/10/test-fixtures-in-go
[3]: https://github.com/argoproj/argo/tree/master/test
[4]: https://github.com/etcd-io/etcd/tree/master/tests
[5]: https://github.com/gopasspw/gopass/tree/master/tests
[6]: https://github.com/helm/helm/tree/master/testdata
[7]: https://github.com/knative/serving/tree/master/test
[8]: https://github.com/kubernetes/kubernetes/tree/master/test
[9]: https://golang.org/cmd/go/#hdr-Package_lists_and_patterns
[10]: https://golang.org/pkg/cmd/go/internal/test
