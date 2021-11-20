<p align="center"><img src="https://raw.githubusercontent.com/svengreb/tmpl-go/main/assets/images/repository-hero.svg?sanitize=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/svengreb/tmpl-go.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a> <a href="https://github.com/svengreb/tmpl-go/blob/main/CHANGELOG.md" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/svengreb/tmpl-go.svg?style=flat-square&label=Changelog&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/actions?query=workflow%3Aci-go" target="_blank"><img src="https://img.shields.io/github/workflow/status/svengreb/tmpl-go/ci-go.svg?style=flat-square&label=CI%20Go&logo=github&logoColor=eceff4&colorA=4c566a"/></a> <a href="https://github.com/svengreb/tmpl-go/actions?query=workflow%3Aci-node" target="_blank"><img src="https://img.shields.io/github/workflow/status/svengreb/tmpl-go/ci-node.svg?style=flat-square&label=CI%20Node&logo=github&logoColor=eceff4&colorA=4c566a"/></a></p>

<p align="center"><a href="https://golang.org/doc/effective_go.html#formatting" target="_blank" rel="noreferrer"><img src="https://img.shields.io/static/v1?style=flat-square&label=Go%20Style%20Guide&message=gofmt&logo=go&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a> <a href="https://github.com/arcticicestudio/styleguide-markdown/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-markdown.svg?style=flat-square&label=Markdown%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzOSIgaGVpZ2h0PSIzOSIgdmlld0JveD0iMCAwIDM5IDM5Ij48cGF0aCBmaWxsPSJub25lIiBzdHJva2U9IiNEOERFRTkiIHN0cm9rZS13aWR0aD0iMyIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiBkPSJNMS41IDEuNWgzNnYzNmgtMzZ6Ii8%2BPHBhdGggZmlsbD0iI0Q4REVFOSIgZD0iTTIwLjY4MyAyNS42NTVsNS44NzItMTMuNDhoLjU2Nmw1Ljg3MyAxMy40OGgtMS45OTZsLTQuMTU5LTEwLjA1Ni00LjE2MSAxMC4wNTZoLTEuOTk1em0tMi42OTYgMGwtMTMuNDgtNS44NzJ2LS41NjZsMTMuNDgtNS44NzJ2MS45OTVMNy45MzEgMTkuNWwxMC4wNTYgNC4xNnoiLz48L3N2Zz4%3D"/></a> <a href="https://github.com/arcticicestudio/styleguide-git/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/arcticicestudio/styleguide-git.svg?style=flat-square&label=Git%20Style%20Guide&logoColor=eceff4&colorA=4c566a&colorB=88c0d0&logo=git"/></a></p>

<p align="center">A <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank" rel="noreferrer">template repository</a> for <a href="https://go.dev" target="_blank" rel="noreferrer">Go</a> projects.</p>

Starting a new project repository means to spend a lot of time first for setting up the basic structure and configuration for the used technology stack over and over again. It is a repetitive task since the same tools are often used across many projects, like linters and code formatters, and therefore often just copied over. This has the disadvantage that the configuration or documentation may differ between different projects or common changes and configurations are not synchronize at all. Many tools provide a way to created so called “shared configurations“ that can be used as base and dynamically composed with project-specific configurations, however, this does not apply to all.
To prevent such problems a central place, so called “template repository“, for basic configurations and documentations as well as focus on different use cases, project structures and programming languages is a good solution to act as a single-source-of-truth™️.

_tmpl-go_, the imaginative abbreviation for “template Go“, is my solution to enable a smooth start for [Go][1] projects and ensure that a project stays healthy, stable and up-to-date over time. Thanks to Go's architecture and tooling this repository can be used as [monorepo][73] that can manage multiple Go & web applications or just a single [Go module][64] or package. No matter for what purposes it is used there are no significant changes needed to the repository structure.
Please note that _tmpl-go_ has mainly been created for my personal use in mind. The default configurations of this template might not fit your needs, but it was designed to be flexible and can be adapted to different use cases and environments.

## Overview

This repository serves as a template for [Go][1] projects including basic tools and configurations with sane default values.
It is built on top of the [base _tmpl_ repository][14] which provides essential features for all kind of projects. Please see the [_tmpl_ project overview documentation][52] for more details.

- [Build on top of the base _tmpl_ template repository][14] that provides essential features for any project
- Extended configurations for [GitHub specific features](#github) that are already provided in the base _tmpl_ template repository:
  - [CI/CD action workflows](#cicd-action-workflows) for Go specific tasks
  - [Automated updates and security vulnerability alerts](#automated-dependency-updates) for [Go Module][64] and [Yarn][3]/[npm][2] dependencies through the native [Dependabot][5] integration
- [Go Module](#go-module) to ensure a stable dependency management
- [golangci-lint][6] to [check the Go code quality](#go-code-quality-linting)

See the [“Features“](#features) section below for more details.

## Directory Structure

The directory structure shown below is derived from the [base _tmpl_ template repository][14] on which this project is based on. Please see the [“Directory Structure“][72] section in the _tmpl_ documentation for more details.

```raw
tmpl-go
├─ .github
│   ├─ ISSUE_TEMPLATE
│   └─ workflows
└─ assets
    └─ images
```

The next directory structure shown below is specially designed for Go projects with [monorepo][73] layout where some parts were adapted from the [golang-standards/project-layout][11] and [ardanlabs/service][12] repositories while others are added through experience with own projects and inspiration from other large, production-grade and well-known projects of the Go ecosystem.

```raw
tmpl-go
├─ api
├─ apps
├─ config
├─ docs
├─ examples
├─ internal
├─ pkg
├─ test
└─ web
```

Please see the [“Features“](#features) section below for more details about provided files in this template repository. The detailed documentation about each directory is located in individual `README.md` files within the directory itself.

- [`/api`][54] — The directory for API definition files like [Protocol Buffers][9], [JSON schemas][10] or [OpenAPI][7]/[Swagger][8] specifications. See the [dedicated `/api` directory documentation][27] for more details and usage examples.
- [`/apps`][55] — The directory for project application(s) using the Go `main` package that can be compiled to the binary executable. See the [dedicated `/apps` directory documentation][28] for more details and usage examples.
- [`/config`][56] — The directory for all configurations such as container orchestration deployments, templates for applications or distribution bundles. See the [dedicated `/config` directory documentation][29] for more details and usage examples.
- [`/docs`][57] — The directory for project documentations, [runbooks][74] and any other kind of textual reference.. See the [dedicated `/docs` directory documentation][30] for more details and usage examples.
- [`/examples`][58] — The directory for all configurations such as container orchestration deployments, templates for applications or distribution bundles. See the [dedicated `/examples` directory documentation][33] for more details and usage examples.
- [`/internal`][59] — The directory for non-exported (“private“) application and package code. See the [dedicated `/internal` directory documentation][36] for more details and usage examples.
- [`/pkg`][60] — The directory for exported (“public“) APIs and package code. See the [dedicated `/pkg` directory documentation][38] for more details and usage examples.
- [`/test`][61] — The directory for additional data and tools for automated testing. See the [dedicated `/test` directory documentation][39] for more details and usage examples.
- [`/web`][62] — The directory for web specific data like [SPA][75]s, static websites, web components & packages or server-side rendered templates that are often built with [JAMStack][4] principles. See the [dedicated `/web` directory documentation][42] for more details and usage examples.

## Features

This repository serves as a template repository for [Go][1] projects that provides essential features.

The sections below contain more detailed information about each feature, the sane default configurations and their files in the repository as well as ways to customize and adjust them to adapt to other use cases and projects. They provide details about files in this repository and the overall directory structure.

### GitHub

This template repository has partially been designed for repositories hosted on GitHub and makes use of many of [its fantastic features][49].

#### CI/CD Action Workflows

The [GitHub Actions][48] `.github/workflows` directory includes a basic [CI/CD workflow files][44] that run for changes in the Git `main` branch and `v*` tags. The `lint-node` job is [derived from the _tmpl_ template repository][51] and runs all [Node.js based linters][52] that are also included in this template repository. The `ci-go` workflow runs all [configured `golangci-lint` linters](#go-code-quality-linting) and the `test` job runs all [tests with coverage report][63] and enabled [race detector][67].
To skip a workflow, include a [supported keyword like `[skip actions]`][43] in a commit message.

#### Automated Dependency Updates

Next to the [Dependabot configuration derived from the base _tmpl_ template repository][50] the [`dependabot.yml` file][31] additionally additionally includes [configurations][45] for [Go Module](#go-module) dependencies.

Make sure to read the [_tmpl_ template repository documentation about automated dependency updates][50] to learn how to enable or disable Dependabot for a GitHub repository.

### Go Module

The [`go.mod`][65] and [`go.sum`][66] files contain information about the [Go Module][64]. See the [official Go Module reference documentation][64], the [“Modules“ page in the GitHub repository wiki][71] and the [“Create a Go module“ tutorial][69] for more details.

### Go Code Quality Linting

To ensure a good code quality the Go ecosystem has hundreds of linters, each with a different purpose. Instead of installing and running multiple linters separately [golangci-lint][6] provides a uniform interface to run most popular and useful linters in parallel with many additional configuration features.
The actual runner is open source and can be used locally as well in any private CI/CD pipeline.
The [`.golangci.yml` configuration file][32] is located in the root of this template repository and comes with sane default configurations that can be simply adjusted and extended.

The runner is also used in the [the existing _CI_ GitHub action workflows][26] through the [golangci-lint-action][13] GitHub action that has been created by the golangci-lint maintainers. See the [“CI/CD Action Workflows“](#cicd-action-workflows) section for more details.

## Usage

There are multiple ways to use this template repository, either by [using GitHubs feature to create a repository from a template][47] or simply [cloning it][46]. No matter which method is used, there are a few manual steps to adjust some configurations and documentations for the individual target project. Note that these changes are only recommendations, but are common steps anyway.

1. Follow the [usage steps of the base _tmpl_ repository][53].
2. Adjust or delete the directories and their dedicated documentations of the [“Directory Structure“ section](#directory-structure) to fit your project setup.
3. Adjust the [`go.mod` file][34]…
   - …so that the value of the `module` attribute matches your projects [Go Module](#go-module) name.
   - …so that the value of the `go` attribute matches the [Go version][68] used by your project.
   - …by deleting the already defined `github.com/stretchr/testify` module dependency when it is not used to write tests for your project.
4. Ensure the [`go.sum` file][35] matches the `go.mod` file by deleting it and running `go mod tidy` so Go resolves the dependency tree with the latest module versions.
   - …by editing it manually and remove entries of unused dependencies.
5. Adjust or delete the [`tmpl-go.go`][41] and [`tmpl-go_test.go`][40] files to match your project.
6. Adjust or delete the `workspaces` field of the [`package.json` file][37] to match your project.

## References

Next to the experience with own projects, many other large, production-grade and well-known projects of the Go ecosystem as well as the [`golang-standards/project-layout` documentation about Go specific directories][70] were used as references.

## Contributing

_tmpl-go_ is an open source project and contributions are always welcome!

There are many ways to contribute, from [writing- and improving documentation and tutorials][17], [reporting bugs][16], [submitting enhancement suggestions][18] that can be added to _tmpl-go_ by [submitting pull requests][22].

Please take a moment to read the [contributing guide][25] to learn about the development process, the [styleguides][23] to which this project adheres as well as the [branch organization][15] and [versioning][24] model.

The guide also includes information about [minimal, complete, and verifiable examples][21] and other ways to contribute to the project like [improving existing issues][20] and [giving feedback on issues and pull requests][19].

<p align="center">Copyright &copy; 2020-present <a href="https://www.svengreb.de" target="_blank" rel="noreferrer">Sven Greb</a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/blob/main/LICENSE" target="_blank" rel="noreferrer"><img src="https://img.shields.io/static/v1.svg?style=flat-square&label=License&message=MIT&logoColor=eceff4&logo=github&colorA=4c566a&colorB=88c0d0"/></a></p>

[1]: https://go.dev
[2]: https://www.npmjs.com
[3]: https://yarnpkg.com
[4]: https://jamstack.org
[5]: https://dependabot.com
[6]: https://github.com/golangci/golangci-lint
[7]: https://www.openapis.org
[8]: https://swagger.io
[9]: https://developers.google.com/protocol-buffers
[10]: https://json-schema.org
[11]: https://github.com/golang-standards/project-layout
[12]: https://github.com/ardanlabs/service
[13]: https://github.com/golangci/golangci-lint-action
[14]: https://github.com/svengreb/tmpl
[15]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#branch-organization
[16]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#bug-reports
[17]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#documentations
[18]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#enhancement-suggestions
[19]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#give-feedback-on-issues-and-pull-requests
[20]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#improve-issues
[21]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#mcve
[22]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#pull-requests
[23]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#style-guides
[24]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md#versioning
[25]: https://github.com/svengreb/tmpl-go/blob/main/CONTRIBUTING.md
[26]: https://github.com/svengreb/tmpl-go/actions?query=workflow%3Aci
[27]: https://github.com/svengreb/tmpl-go/blob/main/api/README.md
[28]: https://github.com/svengreb/tmpl-go/blob/main/apps/README.md
[29]: https://github.com/svengreb/tmpl-go/blob/main/config/README.md
[30]: https://github.com/svengreb/tmpl-go/blob/main/docs/README.md
[31]: https://github.com/svengreb/tmpl-go/blob/main/.github/dependabot.yml
[32]: https://github.com/svengreb/tmpl-go/blob/main/.golangci.yml
[33]: https://github.com/svengreb/tmpl-go/blob/main/examples/README.md
[34]: https://github.com/svengreb/tmpl-go/blob/main/go.mod
[35]: https://github.com/svengreb/tmpl-go/blob/main/go.sum
[36]: https://github.com/svengreb/tmpl-go/blob/main/internal/README.md
[37]: https://github.com/svengreb/tmpl-go/blob/main/package.json
[38]: https://github.com/svengreb/tmpl-go/blob/main/pkg/README.md
[39]: https://github.com/svengreb/tmpl-go/blob/main/test/README.md
[40]: https://github.com/svengreb/tmpl-go/blob/main/tmpl-go_test.go
[41]: https://github.com/svengreb/tmpl-go/blob/main/tmpl-go.go
[42]: https://github.com/svengreb/tmpl-go/blob/main/web/README.md
[43]: https://github.blog/changelog/2021-02-08-github-actions-skip-pull-request-and-push-workflows-with-skip-ci
[44]: https://docs.github.com/en/free-pro-team@latest/actions/reference/workflow-syntax-for-github-actions
[45]: https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/configuration-options-for-dependency-updates
[46]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository
[47]: https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template
[48]: https://github.com/features/actions
[49]: https://github.com/features
[50]: https://github.com/svengreb/tmpl#automated-dependency-updates
[51]: https://github.com/svengreb/tmpl#cicd-action-workflow
[52]: https://github.com/svengreb/tmpl#overview
[53]: https://github.com/svengreb/tmpl#usage
[54]: https://github.com/svengreb/tmpl-go/tree/main/api
[55]: https://github.com/svengreb/tmpl-go/tree/main/apps
[56]: https://github.com/svengreb/tmpl-go/tree/main/config
[57]: https://github.com/svengreb/tmpl-go/tree/main/docs
[58]: https://github.com/svengreb/tmpl-go/tree/main/examples
[59]: https://github.com/svengreb/tmpl-go/tree/main/internal
[60]: https://github.com/svengreb/tmpl-go/tree/main/pkg
[61]: https://github.com/svengreb/tmpl-go/tree/main/test
[62]: https://github.com/svengreb/tmpl-go/tree/main/web
[63]: https://golang.org/cmd/cover
[64]: https://golang.org/ref/mod
[65]: https://golang.org/ref/mod#go-mod-file
[66]: https://golang.org/ref/mod#go
[67]: https://golang.org/doc/articles/race_detector.html
[68]: https://golang.org/doc/devel/release.html
[69]: https://golang.org/doc/tutorial/create-module
[70]: https://github.com/golang-standards/project-layout#go-directories
[71]: https://github.com/golang/go/wiki/Modules
[72]: https://github.com/svengreb/tmpl#directory-structure
[73]: https://trunkbaseddevelopment.com/monorepos
[74]: https://en.wikipedia.org/wiki/Runbook
[75]: https://en.wikipedia.org/wiki/Single-page_application
