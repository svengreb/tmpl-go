The `/api` directory stores API definition files like for example…

- [Protocol Buffers][4]
- [OpenAPI][2]/[Swagger][1] specifications
- [JSON schemas][10]

## Directory Structure

A common practice is that API definition files are placed corresponding to the versioning model and path structure of the API. Please see the section below for a [practical usage example](#example) below for a common and practical usage pattern.

## Example

When using [Protocol Buffer][4] the official style guide also recommends to lay out the directory structure for the `.proto` files based on the API version and [package paths][11].

This example assumes an API that has been designed to manage notes. It uses a [flat major based versioning format][5] starting at `v1`.
The `api` directory structure could be constructed as follows:

```raw
api
└─ v1
   └─ notes
      ├─ states
      │  └─ kinds.proto
      └─ notes.proto
```

The `api/v1/notes/notes.proto` and `api/v1/notes/states/kinds.proto` files could be defined as follows:

```proto
syntax = "proto3";

package tmplgo.api.v1.notes;

import "notes/states/kinds.proto";

option go_package = "github.com/svengreb/tmpl-go/pkg/api/v1/notes";

message Metadata {
  string id = 1;
  string name = 2;
  string creator = 3;
  google.protobuf.Timestamp created = 4;
  google.protobuf.Timestamp modified = 5;
}

message Note {
  Metadata metadata = 1;
  repeated google.protobuf.Timestamp alerts = 2;
  tmplgo.api.v1.notes.states.Kind state = 3;
  Payload payload = 4;
}

message Payload {
  string value = 1;
}

```

```proto
syntax = "proto3";

package tmplgo.api.v1.notes.states;

option go_package = "github.com/svengreb/tmpl-go/pkg/api/v1/notes/states";

enum Kind {
  UNKNOWN = 0;
  OPEN = 1;
  ARCHIVED = 2;
}

```

## References

Next to the experience with own projects and [golang-standards/project-layout][3], many other large, production-grade and well-known projects of the API design and Go ecosystem have been used as references:

- [Google APIs][6]
- [Kubernetes][7]
- [Moby][8]
- [NATS JetStream][9]

[1]: https://swagger.io
[2]: https://www.openapis.org
[3]: https://github.com/golang-standards/project-layout
[4]: https://developers.google.com/protocol-buffers
[5]: https://cloud.google.com/blog/products/gcp/api-design-which-version-of-versioning-is-right-for-you
[6]: https://github.com/googleapis/googleapis
[7]: https://github.com/kubernetes/kubernetes/tree/master/api
[8]: https://github.com/moby/moby/tree/master/api
[9]: https://github.com/nats-io/jetstream/tree/master/schemas_source
[10]: https://json-schema.org
[11]: https://developers.google.com/protocol-buffers/docs/style#packages
