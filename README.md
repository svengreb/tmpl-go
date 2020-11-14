<p align="center"><img src="https://raw.githubusercontent.com/svengreb/tmpl-go/main/assets/images/repository-hero.svg?sanitize=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/releases/latest"><img src="https://img.shields.io/github/release/svengreb/tmpl.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a> <a href="https://github.com/svengreb/tmpl-go/blob/main/CHANGELOG.md"><img src="https://img.shields.io/github/release/svengreb/tmpl.svg?style=flat-square&label=Changelog&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/actions?query=workflow%3Aci" target="_blank"><img src="https://img.shields.io/github/workflow/status/svengreb/tmpl-go/ci.svg?style=flat-square&label=CI&logo=github&logoColor=eceff4&colorA=4c566a"/></a></p>

<p align="center"><a href="https://golang.org/doc/effective_go.html#formatting" target="_blank"><img src="https://img.shields.io/static/v1?style=flat-square&label=Go%20Style%20Guide&message=gofmt&logo=go&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a> <a href="https://github.com/arcticicestudio/styleguide-markdown/releases/latest" target="_blank"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-markdown.svg?style=flat-square&label=Markdown%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzOSIgaGVpZ2h0PSIzOSIgdmlld0JveD0iMCAwIDM5IDM5Ij48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiNEOERFRTkiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMS41IDEuNWgzNnYzNmgtMzZ6Ii8%2BPHBhdGggZmlsbD0iI0Q4REVFOSIgZD0iTTIwLjY4MyAyNS42NTVsNS44NzItMTMuNDhoLjU2Nmw1Ljg3MyAxMy40OGgtMS45OTZsLTQuMTU5LTEwLjA1Ni00LjE2MSAxMC4wNTZoLTEuOTk1em0tMi42OTYgMGwtMTMuNDgtNS44NzJ2LS41NjZsMTMuNDgtNS44NzJ2MS45OTVMNy45MzEgMTkuNWwxMC4wNTYgNC4xNnoiLz48L3N2Zz4%3D"/></a> <a href="https://github.com/arcticicestudio/styleguide-git/releases/latest" target="_blank"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-git.svg?style=flat-square&label=Git%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=git"/></a></p>

<p align="center">A <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank">template repository</a> for <a href="https://go.dev" target="_blank">Go</a> projects.</p>

Starting a new project repository means to spend a lot of time first for setting up the basic structure and configuration for the used technology stack over and over again. It is a repetitive task since the same tools are often used across many projects, like linters and code formatters, and therefore often just copied over. This has the disadvantage that the configuration or documentation may differ between different projects or common changes and configurations are not synchronize at all. Many tools provide a way to created so called “shared configurations“ that can be used as base and dynamically composed with project-specific configurations, however, this does not apply to all.
To prevent such problems a central place, so called “template repository“, for basic configurations and documentations as well as focus on different use cases, project structures and programming languages is a good solution to act as a single-source-of-truth™️.

_tmpl-go_, the imaginative abbreviation for “template Go“, is my solution to enable a smooth start for [Go][] projects and ensure that a project stays healthy, stable and up-to-date over time. Thanks to Go's architecture and tooling this repository can be used as [monorepo][trunkbasedev-monorepos] that can manage multiple Go & web applications or just a single [Go module][go-doc-mod] or package. No matter for what purposes it is used there are no significant changes needed to the repository structure.
Please note that _tmpl-go_ has mainly been created for my personal use in mind. The default configurations of this template might not fit your needs, but it was designed to be flexible and can be adapted to different use cases and environments.

## Overview

This repository serves as a template for [Go][] projects including basic tools and configurations with sane default values.
It is built on top of the [base _tmpl_ repository][tmpl] which provides essential features for all kind of projects. Please see the [_tmpl_ project overview documentation][tmpl-readme#overview] for more details.

- [Build on top of the base _tmpl_ template repository][tmpl] that provides essential features for any project
- Extended configurations for [GitHub specific features](#github) that are already provided in the base _tmpl_ template repository:
  - [CI/CD action workflow](#cicd-action-workflow) for Go specific tasks
  - [Automated updates and security vulnerability alerts](#automated-dependency-updates) for [Go Module][go-doc-mod] and [Yarn][]/[NPM][] dependencies through the native [Dependabot][] integration
- [Go Module](#go-module) to ensure a stable dependency management
- [golangci-lint][] to [check the Go code quality](#go-code-quality-linting)

See the [“Features“](#features) section below for more details.

## Directory Structure

The directory structure shown below is derived from the [base _tmpl_ template repository][tmpl] on which this project is based on. Please see the [“Directory Structure“][tmpl-readme#dir_struct] section in the _tmpl_ documentation for more details.

```raw
tmpl-go
├─ .github
│   ├─ ISSUE_TEMPLATE
│   └─ workflows
└─ assets
    └─ images
```

The next directory structure shown below is specially designed for Go projects with [monorepo][trunkbasedev-monorepos] layout where some parts were adapted from the [golang-standards/project-layout][] and [ardanlabs/service][] repositories while others are added through experience with own projects and inspiration from other large, production-grade and well-known projects of the Go ecosystem.

```raw
tmpl-go
├─ api
├─ app
├─ config
├─ docs
├─ examples
├─ internal
├─ pkg
├─ test
└─ web
```

Please see the [“Features“](#features) section below for more details about provided files in this template repository. The detailed documentation about each directory is located in individual `README.md` files within the directory itself.

- [`/api`][gh-tree-api] — The directory for API definition files like [Protocol Buffers][protobuf], [JSON schemas][json-schema] or [OpenAPI][]/[Swagger][] specifications. See the [dedicated `/api` directory documentation][gh-blob-api-readme] for more details and usage examples.
- [`/app`][gh-tree-app] — The directory for project application(s) using the Go `main` package that can be compiled to the binary executable. See the [dedicated `/app` directory documentation][gh-blob-app-readme] for more details and usage examples.
- [`/config`][gh-tree-config] — The directory for all configurations such as container orchestration deployments, templates for applications or distribution bundles. See the [dedicated `/config` directory documentation][gh-blob-config-readme] for more details and usage examples.
- [`/docs`][gh-tree-docs] — The directory for project documentations, [runbooks][wikip-runbook] and any other kind of textual reference.. See the [dedicated `/docs` directory documentation][gh-blob-docs-readme] for more details and usage examples.
- [`/examples`][gh-tree-examples] — The directory for all configurations such as container orchestration deployments, templates for applications or distribution bundles. See the [dedicated `/examples` directory documentation][gh-blob-examples-readme] for more details and usage examples.
- [`/internal`][gh-tree-internal] — The directory for non-exported (“private“) application and package code. See the [dedicated `/internal` directory documentation][gh-blob-internal-readme] for more details and usage examples.
- [`/pkg`][gh-tree-pkg] — The directory for exported (“public“) APIs and package code. See the [dedicated `/pkg` directory documentation][gh-blob-pkg-readme] for more details and usage examples.
- [`/test`][gh-tree-test] — The directory for additional data and tools for automated testing. See the [dedicated `/test` directory documentation][gh-blob-test-readme] for more details and usage examples.
- [`/web`][gh-tree-web] — The directory for web specific data like [SPA][wikip-spa]s, static websites, web components & packages or server-side rendered templates that are often built with [JAMStack][] principles. See the [dedicated `/web` directory documentation][gh-blob-web-readme] for more details and usage examples.

## Features

This repository serves as a template repository for [Go][] projects that provides essential features.

The sections below contain more detailed information about each feature, the sane default configurations and their files in the repository as well as ways to customize and adjust them to adapt to other use cases and projects. They provide details about files in this repository and the overall directory structure.

### GitHub

This template repository has partially been designed for repositories hosted on GitHub and makes use of many of [its fantastic features][gh-features].

#### CI/CD Action Workflow

The [GitHub Actions][gh-feat-actions] `.github/workflows` directory includes a basic [CI/CD workflow file][gh-docs-act-ref-syntax] that runs for changes in the Git `main` branch and `v*` tags. The `lint-node` job is [derived from the _tmpl_ template repository][gh-tmpl#gh_act_cicd] and runs all [Node.js based linters][gh-tmpl#ov] that are also included in this template repository. The `lint-go` job runs all [configured `golangci-lint` linters](#go-code-quality-linting) while the `test` job runs all [tests with coverage report][go-doc-cmd-cover] and enabled [race detector][go-doc-race_detector].

#### Automated Dependency Updates

Next to the [Dependabot configuration derived from the base _tmpl_ template repository][gh-tmpl#autp_dep_updates] the [`dependabot.yml` file][gh-blob-dot_github-dependabot.yml] additionally additionally includes [configurations][gh-docs-dependabot] for [Go Module](#go-module) dependencies.

Make sure to read the [_tmpl_ template repository documentation about automated dependency updates][gh-tmpl#autp_dep_updates] to learn how to enable or disable Dependabot for a GitHub repository.

### Go Module

The [`go.mod`][go-doc-mod#file] and [`go.sum`][go-doc-mod#sum_file] files contain information about the [Go Module][go-doc-mod]. See the [official Go Module reference documentation][go-doc-mod], the [“Modules“ page in the GitHub repository wiki][golang/go-wiki-mod] and the [“Create a Go module“ tutorial][go-doc-tut-mod] for more details.

### Go Code Quality Linting

To ensure a good code quality the Go ecosystem has hundreds of linters, each with a different purpose. Instead of installing and running multiple linters separately [golangci-lint][] provides a uniform interface to run most popular and useful linters in parallel with many additional configuration features.
The actual runner is open source and can be used locally as well in any private CI/CD pipeline.
The [`.golangci.yml` configuration file][gh-blob-dot_golangci] is located in the root of this template repository and comes with sane default configurations that can be simply adjusted and extended.

The runner is also used in the [the existing _CI_ GitHub action workflow][gh-act-ci] through the [golangci-lint-action][] GitHub action that has been created by the golangci-lint maintainers. See the [“CI/CD Action Workflow“](#cicd-action-workflow) section for more details.

## Usage

There are multiple ways to use this template repository, either by [using GitHubs feature to create a repository from a template][gh-docs-repo_from_tmpl] or simply [cloning it][gh-docs-repo_clone]. No matter which method is used, there are a few manual steps to adjust some configurations and documentations for the individual target project. Note that these changes are only recommendations, but are common steps anyway.

1. Follow the [usage steps of the base _tmpl_ repository][gh-tmpl#usage].
2. Adjust or delete the directories and their dedicated documentations of the [“Directory Structure“ section](#directory-structure) to fit your project setup.
3. Adjust the [`go.mod` file][gh-blob-go.mod]…
   - …so that the value of the `module` attribute matches your projects [Go Module](#go-module) name.
   - …so that the value of the `go` attribute matches the [Go version][go-doc-rel_hist] used by your project.
   - …by deleting the already defined `github.com/stretchr/testify` module dependency when it is not used to write tests for your project.
4. Ensure the [`go.sum` file][gh-blob-go.sum] matches the `go.mod` file by deleting it and running `go mod tidy` so Go resolves the dependency tree with the latest module versions.
   - …by editing it manually and remove entries of unused dependencies.
5. Adjust or delete the [`tmpl-go.go`][gh-blob-tmpl-go.go] and [`tmpl-go_test.go`][gh-blob-tmpl-go_test.go] files to match your project.
6. Adjust or delete the `workspaces` field of the [`package.json` file][gh-blob-package.json] to match your project.

## References

Next to the experience with own projects, many other large, production-grade and well-known projects of the Go ecosystem as well as the [`golang-standards/project-layout` documentation about Go specific directories][golang-standards/project-layout#go_dirs] were used as references.

## Contributing

_tmpl-go_ is an open source project and contributions are always welcome!

There are many ways to contribute, from [writing- and improving documentation and tutorials][contrib-guide-docs], [reporting bugs][contrib-guide-bugs], [submitting enhancement suggestions][contrib-guide-enhance] that can be added to _tmpl-go_ by [submitting pull requests][contrib-guide-pr].

Please take a moment to read the [contributing guide][contrib-guide] to learn about the development process, the [styleguides][contrib-guide-styles] to which this project adheres as well as the [branch organization][contrib-guide-branching] and [versioning][contrib-guide-versioning] model.

The guide also includes information about [minimal, complete, and verifiable examples][contrib-guide-mcve] and other ways to contribute to the project like [improving existing issues][contrib-guide-impr-issues] and [giving feedback on issues and pull requests][contrib-guide-feedback].

<p align="center">Copyright &copy; 2020-present <a href="https://www.svengreb.de" target="_blank">Sven Greb</a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/blob/main/LICENSE"><img src="https://img.shields.io/static/v1.svg?style=flat-square&label=License&message=MIT&logoColor=eceff4&logo=github&colorA=4c566a&colorB=88c0d0"/></a></p>

[ardanlabs/service]: https://github.com/ardanlabs/service
[contrib-guide-branching]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#branch-organization
[contrib-guide-bugs]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#bug-reports
[contrib-guide-docs]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#documentations
[contrib-guide-enhance]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#enhancement-suggestions
[contrib-guide-feedback]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#give-feedback-on-issues-and-pull-requests
[contrib-guide-impr-issues]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#improve-issues
[contrib-guide-mcve]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#mcve
[contrib-guide-pr]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#pull-requests
[contrib-guide-styles]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#style-guides
[contrib-guide-versioning]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#versioning
[contrib-guide]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md
[dependabot]: https://dependabot.com
[gh-act-ci]: https://github.com/svengreb/tmpl-go/actions?query=workflow%3Aci
[gh-blob-api-readme]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md
[gh-blob-app-readme]: https://github.com/svengreb/tmpl-go/blob/main/app/README.md
[gh-blob-config-readme]: https://github.com/svengreb/tmpl-go/blob/main/config/README.md
[gh-blob-docs-readme]: https://github.com/svengreb/tmpl-go/blob/main/docs/README.md
[gh-blob-dot_github-dependabot.yml]: https://github.com/svengreb/tmpl-go/blob/main/.github/dependabot.yml
[gh-blob-dot_golangci]: https://github.com/svengreb/tmpl-go/blob/main/.golangci.yml
[gh-blob-examples-readme]: https://github.com/svengreb/tmpl-go/blob/main/examples/README.md
[gh-blob-go.mod]: https://github.com/svengreb/tmpl-go/blob/main/go.mod
[gh-blob-go.sum]: https://github.com/svengreb/tmpl-go/blob/main/go.sum
[gh-blob-internal-readme]: https://github.com/svengreb/tmpl-go/blob/main/internal/README.md
[gh-blob-package.json]: https://github.com/svengreb/tmpl-go/blob/main/package.json
[gh-blob-pkg-readme]: https://github.com/svengreb/tmpl-go/blob/main/pkg/README.md
[gh-blob-test-readme]: https://github.com/svengreb/tmpl-go/blob/main/test/README.md
[gh-blob-tmpl-go_test.go]: https://github.com/svengreb/tmpl-go/blob/main/tmpl-go_test.go
[gh-blob-tmpl-go.go]: https://github.com/svengreb/tmpl-go/blob/main/tmpl-go.go
[gh-blob-web-readme]: https://github.com/svengreb/tmpl-go/blob/main/web/README.md
[gh-docs-act-ref-syntax]: https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions
[gh-docs-dependabot]: https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/configuration-options-for-dependency-updates
[gh-docs-repo_clone]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository
[gh-docs-repo_from_tmpl]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template
[gh-feat-actions]: https://github.com/features/actions
[gh-features]: https://github.com/features
[gh-tmpl#autp_dep_updates]: https://github.com/svengreb/tmpl#automated-dependency-updates
[gh-tmpl#gh_act_cicd]: https://github.com/svengreb/tmpl#cicd-action-workflow
[gh-tmpl#ov]: https://github.com/svengreb/tmpl#overview
[gh-tmpl#usage]: https://github.com/svengreb/tmpl#usage
[gh-tree-api]: https://github.com/svengreb/tmpl-go/tree/main/api
[gh-tree-app]: https://github.com/svengreb/tmpl-go/tree/main/app
[gh-tree-config]: https://github.com/svengreb/tmpl-go/tree/main/config
[gh-tree-docs]: https://github.com/svengreb/tmpl-go/tree/main/docs
[gh-tree-examples]: https://github.com/svengreb/tmpl-go/tree/main/examples
[gh-tree-internal]: https://github.com/svengreb/tmpl-go/tree/main/internal
[gh-tree-pkg]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[gh-tree-test]: https://github.com/svengreb/tmpl-go/tree/main/test
[gh-tree-web]: https://github.com/svengreb/tmpl-go/tree/main/web
[go-doc-cmd-cover]: https://golang.org/cmd/cover
[go-doc-mod]: https://golang.org/ref/mod
[go-doc-mod#file]: https://golang.org/ref/mod#go-mod-file
[go-doc-mod#sum_file]: https://golang.org/ref/mod#go
[go-doc-race_detector]: https://golang.org/doc/articles/race_detector.html
[go-doc-rel_hist]: https://golang.org/doc/devel/release.html
[go-doc-tut-mod]: https://golang.org/doc/tutorial/create-module
[go]: https://go.dev
[golang-standards/project-layout]: https://github.com/golang-standards/project-layout
[golang-standards/project-layout#go_dirs]: https://github.com/golang-standards/project-layout#go-directories
[golang/go-wiki-mod]: https://github.com/golang/go/wiki/Modules
[golangci-lint-action]: https://github.com/golangci/golangci-lint-action
[golangci-lint]: https://github.com/golangci/golangci-lint
[jamstack]: https://jamstack.org
[json-schema]: https://json-schema.org
[npm]: https://www.npmjs.com
[openapi]: https://www.openapis.org
[protobuf]: https://developers.google.com/protocol-buffers
[swagger]: https://swagger.io
[tmpl-readme#dir_struct]: https://github.com/svengreb/tmpl#directory-structure
[tmpl-readme#overview]: https://github.com/svengreb/tmpl#overview
[tmpl]: https://github.com/svengreb/tmpl
[trunkbasedev-monorepos]: https://trunkbaseddevelopment.com/monorepos
[wikip-runbook]: https://en.wikipedia.org/wiki/Runbook
[wikip-spa]: https://en.wikipedia.org/wiki/Single-page_application
[yarn]: https://yarnpkg.com
