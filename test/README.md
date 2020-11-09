The `/test` directory, also often named `spec`, stores additional data and tools for automated testing.

Additional external test apps and test data. Feel free to structure the /test directory anyway you want. For bigger projects it makes sense to have a data subdirectory. For example, you can have /test/data or /test/testdata if you need Go to ignore what's in that directory. Note that Go will also ignore directories or files that begin with "." or "\_", so you have more flexibility in terms of how you name your test data directory.

## Directory Structure

The layout always depends on the individual use case(s) of the project, but there are resources like the official documentations of the [`go test` command][go-doc-cmd-test], which includes information about directories named `testdata`, and about [package lists and patterns][go-doc-cmd-go#pkg_list_pattern].

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

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Knative][gh-knative-tree-test]
- [Kubernetes][gh-kubernetes-tree-test]
- [etcd][gh-etcd-tree-tests]
- [Argo][gh-argo-tree-test]
- [Helm][gh-helm-tree-testdata]
- [GoPass][gh-gopass-tree-tests]

Blog posts, videos and documentations:

- [Blog Post: “Test fixtures in Go“][bp-davecheney-test_fixtures]

[bp-davecheney-test_fixtures]: https://dave.cheney.net/2016/05/10/test-fixtures-in-go
[gh-argo-tree-test]: https://github.com/argoproj/argo/tree/master/test
[gh-etcd-tree-tests]: https://github.com/etcd-io/etcd/tree/master/tests
[gh-gopass-tree-tests]: https://github.com/gopasspw/gopass/tree/master/tests
[gh-helm-tree-testdata]: https://github.com/helm/helm/tree/master/testdata
[gh-knative-tree-test]: https://github.com/knative/serving/tree/master/test
[gh-kubernetes-tree-test]: https://github.com/kubernetes/kubernetes/tree/master/test
[go-doc-cmd-go#pkg_list_pattern]: https://golang.org/cmd/go/#hdr-Package_lists_and_patterns
[go-doc-cmd-test]: https://golang.org/pkg/cmd/go/internal/test
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
