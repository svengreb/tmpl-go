The `/web` directory stores web specific data like [SPA][32]s, static websites, web components & packages or server-side rendered templates. These are often build with the [JAMStack][4] principles where…

- …the content is written in formats like [Markdown][31] or [MDX][5] and, depending on the project scope and technology stack, require a preprocessor.
- …the actual applications or web-based documentation are built with [static site generators][28] like [Gatsby][1], [Next.js][6] or [Hugo][3] that leverage reactive UI design through libraries like [React][8] and dynamic styling with [styled components][9].
- …the data is fetched from APIs, often built on top of [GraphQL][2], and rendered into templates and customizable data structures through a headless CMS like [TinaCMS][10] or [Directus][11] so that even non-tech-savvy people can edit and create content.

See references like the [JAMStack][4] documentations for more details.

## Directory Structure

The layout often depends on the individual use case(s) of the project, but it is a good practice to structure it as [monorepo][30] by using [Yarn][33] or [NPM][29] workspaces to store and manage multiple packages and applications. This template repository provides a basic workspace setup that is configured in the [`package.json` file][14].

## Example

Given the API defined in the [example of the `/api` directory][13] the structure could be created as follows:

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

Next to the experience with own projects and [golang-standards/project-layout][12], many other large, production-grade and well-known projects of the Go ecosystem have been used as references:

- [Consul][15] ([Website][16])
- [Vault][25] ([Website][26])
- [Nomad][19] ([Website][20])
- [Drone][17]
- [Traefik][24]
- [Prometheus][22]
- [PhotoPrism][21]
- [GitLab][27]
- [Gitea][18]
- [Satellity][23]

[1]: https://www.gatsbyjs.com
[2]: https://graphql.org
[3]: https://gohugo.io
[4]: https://jamstack.org
[5]: https://mdxjs.com
[6]: https://jamstack.org/generators/next
[8]: https://reactjs.org
[9]: https://styled-components.com
[10]: https://tinacms.org
[11]: https://directus.io
[12]: https://github.com/golang-standards/project-layout
[13]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md#example
[14]: https://github.com/svengreb/tmpl-go/blob/main/package.json
[15]: https://github.com/hashicorp/consul/tree/master/ui
[16]: https://github.com/hashicorp/consul/tree/master/website
[17]: https://github.com/drone/drone/tree/master/web
[18]: https://github.com/go-gitea/gitea/tree/master/web_src
[19]: https://github.com/hashicorp/nomad/tree/master/ui
[20]: https://github.com/hashicorp/nomad/tree/master/website
[21]: https://github.com/photoprism/photoprism/tree/develop/frontend
[22]: https://github.com/prometheus/prometheus/tree/master/web
[23]: https://github.com/satellity/satellity/tree/master/app
[24]: https://github.com/traefik/traefik/tree/master/webui
[25]: https://github.com/hashicorp/vault/tree/master/ui
[26]: https://github.com/hashicorp/vault/tree/master/website
[27]: https://gitlab.com/gitlab-org/gitlab/-/tree/master/app
[28]: https://jamstack.org/generators
[29]: https://docs.npmjs.com/cli/v7/using-npm/workspaces
[30]: https://trunkbaseddevelopment.com/monorepos
[31]: https://en.wikipedia.org/wiki/Markdown
[32]: https://en.wikipedia.org/wiki/Single-page_application
[33]: https://classic.yarnpkg.com/docs/workspaces
