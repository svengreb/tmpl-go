The `/web` directory stores web specific data like [SPA][wikip-spa]s, static websites, web components & packages or server-side rendered templates. These are often build with the [JAMStack][] principles where…

- …the content is written in formats like [Markdown][wikip-md] or [MDX][] and, depending on the project scope and technology stack, require a preprocessor.
- …the actual applications or web-based documentation are built with [static site generators][jamstack-gens] like [Gatsby][], [Next.js][] or [Hugo][] that leverage reactive UI design through libraries like [React][] and dynamic styling with [styled components][styled-components].
- …the data is fetched from APIs, often built on top of [GraphQL][], and rendered into templates and customizable data structures through a headless CMS like [TinaCMS][] or [Directus][] so that even non-tech-savvy people can edit and create content.

See references like the [JAMStack][] documentations for more details.

## Directory Structure

The layout often depends on the individual use case(s) of the project, but it is a good practice to structure it as [monorepo][trunkbasedev-monorepos] by using [Yarn][yarn-docs-ws] or [NPM][npm-docs-cli-v7-ws] workspaces to store and manage multiple packages and applications. This template repository provides a basic workspace setup that is configured in the [`package.json` file][gh-blob-package.json].

## Example

Given the API defined in the [example of the `/api` directory][gh-blob-api-readme#example] the structure could be created as follows:

```raw
web
├─ api
│  └─ notes
│     └─ v1
│        └─ states
├─ apps
│  ├─ notes
│  │  ├─ src
│  │  │  ├─ components
│  │  │  └─ views
│  │  └─ typings
│  └─ notes-sync
│     ├─ src
│     │  └─ platform
│     │     └─ messaging
│     └─ typings
├─ packages
│  └─ @notes
│     ├─ docs
│     │  └─ content
│     └─ ui
│        └─ src
│           ├─ components
│           ├─ hooks
│           ├─ styles
│           └─ utils
├─ www
│  ├─ assets
│  ├─ src
│  │  ├─ assets
│  │  ├─ components
│  │  ├─ data
│  │  ├─ hooks
│  │  ├─ pages
│  │  ├─ styles
│  │  └─ utils
│  └─ test
└─ utils
   ├─ eslint
   └─ scripts
```

## References

Next to the experience with own projects and [golang-standards/project-layout][], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Consul][gh-consul-tree-ui] ([Website][gh-consul-tree-website])
- [Vault][gh-vault-tree-ui] ([Website][gh-vault-tree-website])
- [Nomad][gh-nomad-tree-ui] ([Website][gh-nomad-tree-website])
- [Drone][gh-drone-tree-web]
- [Traefik][gh-traefik-tree-webui]
- [Prometheus][gh-prometheus-tree-web]
- [PhotoPrism][gh-photoprism-tree-frontend]
- [GitLab][gl-gitlab-tree-app]
- [Gitea][gh-gitea-tree-web_src]
- [Satellity][gh-satellity-tree-app]

[directus]: https://directus.io
[gatsby]: https://www.gatsbyjs.com
[gh-blob-api-readme#example]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[gh-blob-package.json]: https://github.com/svengreb/tmpl-go/blob/main/package.json
[gh-consul-tree-ui]: https://github.com/hashicorp/consul/tree/master/ui
[gh-consul-tree-website]: https://github.com/hashicorp/consul/tree/master/website
[gh-drone-tree-web]: https://github.com/drone/drone/tree/master/web
[gh-gitea-tree-web_src]: https://github.com/go-gitea/gitea/tree/master/web_src
[gh-nomad-tree-ui]: https://github.com/hashicorp/nomad/tree/master/ui
[gh-nomad-tree-website]: https://github.com/hashicorp/nomad/tree/master/website
[gh-photoprism-tree-frontend]: https://github.com/photoprism/photoprism/tree/develop/frontend
[gh-prometheus-tree-web]: https://github.com/prometheus/prometheus/tree/master/web
[gh-satellity-tree-app]: https://github.com/satellity/satellity/tree/master/app
[gh-traefik-tree-webui]: https://github.com/traefik/traefik/tree/master/webui
[gh-vault-tree-ui]: https://github.com/hashicorp/vault/tree/master/ui
[gh-vault-tree-website]: https://github.com/hashicorp/vault/tree/master/website
[gl-gitlab-tree-app]: https://gitlab.com/gitlab-org/gitlab/-/tree/master/app
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
[graphql]: https://graphql.org
[hugo]: https://gohugo.io
[jamstack-gens]: https://jamstack.org/generators
[jamstack]: https://jamstack.org
[mdx]: https://mdxjs.com
[next.js]: https://jamstack.org/generators/next
[npm-docs-cli-v7-ws]: https://docs.npmjs.com/cli/v7/using-npm/workspaces
[react]: https://reactjs.org
[styled-components]: https://styled-components.com
[tinacms]: https://tinacms.org
[trunkbasedev-monorepos]: https://trunkbaseddevelopment.com/monorepos
[wikip-md]: https://en.wikipedia.org/wiki/Markdown
[wikip-spa]: https://en.wikipedia.org/wiki/Single-page_application
[yarn-docs-ws]: https://classic.yarnpkg.com/docs/workspaces
