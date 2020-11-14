<p align="center"><img src="https://raw.githubusercontent.com/svengreb/tmpl-go/main/assets/images/repository-hero.svg?sanitize=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/releases/latest"><img src="https://img.shields.io/github/release/svengreb/tmpl-go.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center">Changelog of the <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank">template repository</a> for Go projects.</p>

<!--lint disable no-duplicate-headings no-duplicate-headings-in-section-->

# 0.5.0

![Release Date: 2020-11-10](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-11-10&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.5.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/9) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.5.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/6)

⇅ [Show all commits][repo-compare-tag-v0.4.0_v0.5.0]

## Features

<details>
<summary><strong>Initial project documentation</strong> — #31 ⇄ #32 (⊶ d1a77a3d)</summary>

↠ Wrote the initial project documentation for the `README.md` file that includes…

1. …an project introduction and motivation.
2. …an overview of the project features.
3. …an overview of the directory structure.
4. …more detailed sections about all features.
5. …some basic instructions how to use this template repository.
6. …information about references used for this template repository.
7. …information about how to contribute to this project.

Each directory documented in step 3 contains an individual documentation with more detailed information about it.
The `package.json` file has also been extended to include the [Yarn][yarn-docs-ws]/[NPM][npm-docs-cli-v7-ws] `workspaces` field.

</details>

<details>
<summary><strong>Update to <code>tmpl</code> template repository version 0.7.0</strong> — #24, #33 ⇄ #25, #34 (⊶ 793efc26, 81385803)</summary>

↠ Updated to [`tmpl` version 0.7.0][gh-tmpl-rel-v0.7.0] (including version [0.6.0][gh-tmpl-rel-v0.6.0]) which introduced a configuration for [automated dependency updates and security alerts][svengreb/tmpl#52] with [Dependabot][]. Next to the included update configurations for the [CI/CD GitHub action workflow][tmpl#cicd] and [Yarn/NPM dependencies][tmpl#node], the file has been extended to support [Go modules][go-doc-mod].
This version also updated to the latest Node.js package dependency & GitHub Action versions.

</details>

# 0.4.0

![Release Date: 2020-10-31](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-10-31&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.4.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/8) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.4.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/5)

⇅ [Show all commits][repo-compare-tag-v0.3.0_v0.4.0]

## Features

<details>
<summary><strong>Update to golangci-lint version 1.32.0</strong> — #20 ⇄ #21 (⊶ 072aad99)</summary>

↠ The currently latest [`golangci-lint` version 1.32.0][golangci-lint-rln-1.32.0] introduced new linters that have been configured for this template repository:

1. [wrapcheck][] — Checks that errors returned from external packages are wrapped.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help tp reduce error context loss.
2. [errorlint][] — Helps to make more efficient use of the error wrapping scheme introduced in Go 1.13.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help to use Go's new error handling concept.
3. [tparallel][] — Detects inappropriate usage of `t.Parallel()` method in Go tests.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help to prevent parallelism errors in tests.

</details>

<details>
<summary><strong>Update to "tmpl" template repository version 0.5.0</strong> — #22 ⇄ #23 (⊶ 5da341c3)</summary>

↠ Updated to ["tmpl" version 0.5.0][gh-tmpl-rel-v0.5.0] which now uses a [namespace for the NPM package name][svengreb/tmpl#48] that helps to prevent collisions with already existing NPM packages like [tmpl][npm-tmpl].

</details>

# 0.3.0

![Release Date: 2020-09-25](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-25&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.3.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/7) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.3.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/4)

⇅ [Show all commits][repo-compare-tag-v0.2.0_v0.3.0]

## Features

<details>
<summary><strong>Go stub package and test</strong> — #12 ⇄ #13 (⊶ 66658a15)</summary>

↠ To prevent `golangci-lint` and the CI workflow `test` job from failing a stub file for the `tmplgo` package has been added along with a example test (`tmplgo_test` package).
This also comes with the benefit of providing a simple starting point for users of this template repository.

</details>

## Improvements

<details>
<summary><strong>Optimize Go version matrix strategy for CI workflow</strong> — #16 ⇄ #17 (⊶ bda13d8a)</summary>

↠ Before the CI workflow used a matrix strategy to run the `lint-go` and `test` jobs, but this has been improved to make the workflow run faster by avoiding unnecessary steps:

- The `lint-go` job has been changed to only run on the [currently latest stable Go version `1.15.x`][go-rln-go-1.15] only on _Linux_ because `golangci-lint` doesn't care about the _Go_ version and OS it runs on but only statically checks the source code.
- The `test` job has been changed to only run on the [currently latest stable Go version `1.15.x`][go-rln-go-1.15].

These changes help to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary tasks.

</details>

<details>
<summary><strong>Adapt CI workflow "on" run configurations from "tmpl" template repository</strong> — #18 ⇄ #19 (⊶ ec1539cd)</summary>

↠ Before the CI workflow only used the `push` configuration for the `on` field. To improve the performance a more fine grained configuration is now used that has already been defined in [the "tmpl" template repository][gh-tmpl]:

- Only runs on pushes to the `main` branch.
- Only runs on pushes for `v*` tags.
- Always runs for pushes to PRs.

These changes help to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary runs.

</details>

## Tasks

<details>
<summary><strong>Adapt to "tmpl" template repository version 0.4.0</strong> — #14 ⇄ #15 (⊶ 9d50ec0e)</summary>

↠ Adapted to ["tmpl" version 0.4.0][gh-tmpl-rel-v0.4.0] which includes a [optimized OS version matrix strategy for Node based tasks in the CI workflow][svengreb/tmpl#46] that helps to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary tasks.

</details>

# 0.2.0

![Release Date: 2020-09-24](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-24&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.2.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/6) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.2.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/3)

⇅ [Show all commits][repo-compare-tag-v0.1.1_v0.2.0]

## Features

<details>
<summary><strong>Basic testing in CI workflow</strong> — #10 ⇄ #11 (⊶ f65759e6)</summary>

↠ Before the CI workflow only ran _Node_ and _Go_ based linters, but doesn't took _Go_ tests into account. This has been changed by adding a new job to run tests with _Go_'s official `go test` command with enabled coverage and race detector.

</details>

# 0.1.1

![Release Date: 2020-09-21](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-21&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.1.1&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/5) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.1.1&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/2)

⇅ [Show all commits][repo-compare-tag-v0.1.0_v0.1.1]

## Bug Fixes

<details>
<summary><strong>YAML multiline string without "block chomping" for config go-header linter causes golangci-lint to fail</strong> — #6 ⇄ #7 (⊶ 910c06ff)</summary>

↠ The configuration of the [go-header][] linter is defined in the [golangci-lint][] YAML configuration, but the [YAML multiline-string][yaml-multiline] doesn't used ["block chomping][yaml-spec-1.2#block_chomping] which resulted in a final newline at the end of the template.
This caused golangci-lint to fail because the configured template content doesn't match the parsed text.
To fix this problem the YAML _block chomping_ syntax is now used for the multiline-string so that the final newline at the end gets stripped.

</details>

<details>
<summary><strong>Invalid branch & CI workflow name in README badges </strong> — #8 ⇄ #9 (⊶ e138ca15)</summary>

↠ The name of the branch for the badge URL of the repository changelog was `master` instead of `main` and the GitHub CI action workflow used the uppercase name `CI` instead of `ci`.

</details>

# 0.1.0

![Release Date: 2020-09-20](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-20&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/4) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/1)

⇅ [Show all commits][repo-compare-tag-init_v0.1.0]

This is the initial release version of _tmpl-go_.
The basic project setup, structure and development workflow has been bootstrapped by [the base _tmpl_ template repository][gh-tmpl].
The additional Go specific initial configurations and documentations are covered in the following sections of this version changelog to introduce used technologies and explain why several decisions have been made.

## Features

<details>
<summary><strong>Bootstrap from "tmpl" base template repository</strong> — #1 (⊶ 87400d37)</summary>

<p align="center"><img src="https://github.com/svengreb/tmpl/blob/main/assets/images/repository-hero-base.svg?raw=true"/></p>

↠ Bootstrapped the basic project setup, structure and development workflow [from version 0.3.0][gh-tmpl-release-v0.3.0] of the [base "tmpl" template repository][gh-tmpl].
Additionally specific assets like the repository hero image were also added.

</details>

<details>
<summary><strong>Go Module</strong> — #1 ⇄ #3 (⊶ 52bea37b)</summary>

↠ tmpl-go uses the currently latest Go version [1.15.0][go-rln-1.15.0] with [Go Modules][gh-go-wiki-modules] and `github.com/svengreb/tmpl-go` as module name.

</details>

<details>
<summary><strong>Code quality with "golangci-lint"</strong> — #4 ⇄ #5 (⊶ b20e205f)</summary>

↠ To ensure a good code quality the Go ecosystem has hundreds of linters, each with a different purpose. Instead of installing and running multiple linters separately [golangci-lint][] provides a uniform interface to run most popular and useful linters in parallel and with many additional configuration features.
The actual runner is open source and can be used locally as well in any private CI/CD pipeline. In order to use it for tmpl-go, a `.golangci.yml` configuration file has been added.

The runner is used in the [the existing _CI_ GitHub action workflow][repo-action-query-ci] through the [golangci-lint-action][] GitHub action that has been created by the golangci-lint maintainers.

</details>

<!--
+------------------+
+ Formatting Notes +
+------------------+

The `<summary />` tag must be separated with a blank line from the actual item content paragraph,
otherwise Markdown elements are not parsed and rendered!

+------------------+
+ Symbol Reference +
+------------------+
↠ (U+21A0): Start of a log section description
— (U+2014): Separator between a log section title and the metadata
⇄ (U+21C4): Separator between a issue ID and pull request ID in a log metadata
⊶ (U+22B6): Icon prefix for the short commit SHA checksum in a log metadata
⇅ (U+21C5): Icon prefix for the link of the Git commit history comparison on GitHub
-->

<!--lint disable final-definition-->

<!-- Base Links -->

[gh-tmpl]: https://github.com/svengreb/tmpl
[golangci-lint]: https://github.com/golangci/golangci-lint

<!-- v0.1.0 -->

[gh-go-wiki-modules]: https://github.com/golang/go/wiki/Modules
[gh-tmpl-release-v0.3.0]: https://github.com/svengreb/tmpl/releases/tag/v0.3.0
[go-rln-1.15.0]: https://golang.org/doc/go1.15
[golangci-lint-action]: https://github.com/golangci/golangci-lint-action
[repo-action-query-ci]: https://github.com/svengreb/tmpl-go/actions?query=workflow%3ACI
[repo-compare-tag-init_v0.1.0]: https://github.com/svengreb/tmpl-go/compare/87400d37...v0.1.0

<!-- v0.1.1 -->

[go-header]: https://github.com/denis-tingajkin/go-header
[repo-compare-tag-v0.1.0_v0.1.1]: https://github.com/svengreb/tmpl-go/compare/v0.1.0...v0.1.1
[yaml-multiline]: https://yaml-multiline.info
[yaml-spec-1.2#block_chomping]: https://yaml.org/spec/1.2/spec.html#id2794534

<!-- v0.2.0 -->

[repo-compare-tag-v0.1.1_v0.2.0]: https://github.com/svengreb/tmpl-go/compare/v0.1.1...v0.2.0

<!-- v0.3.0 -->

[gh-tmpl-rel-v0.4.0]: https://github.com/svengreb/tmpl/releases/tag/v0.4.0
[go-rln-go-1.15]: https://golang.org/doc/go1.15
[repo-compare-tag-v0.2.0_v0.3.0]: https://github.com/svengreb/tmpl-go/compare/v0.2.0...v0.3.0
[svengreb/tmpl#46]: https://github.com/svengreb/tmpl/issues/46

<!-- v0.4.0 -->

[errorlint]: https://github.com/polyfloyd/go-errorlint
[gh-tmpl-rel-v0.5.0]: https://github.com/svengreb/tmpl/releases/tag/v0.5.0
[golangci-lint-rln-1.32.0]: https://github.com/golangci/golangci-lint/releases/tag/v1.32.0
[npm-tmpl]: https://www.npmjs.com/package/tmpl
[repo-compare-tag-v0.3.0_v0.4.0]: https://github.com/svengreb/tmpl-go/compare/v0.3.0...v0.4.0
[svengreb/tmpl#48]: https://github.com/svengreb/tmpl/issues/48
[tparallel]: https://github.com/moricho/tparallel
[wrapcheck]: https://github.com/tomarrell/wrapcheck

<!-- v0.5.0 -->

[dependabot]: https://dependabot.com
[gh-tmpl-rel-v0.6.0]: https://github.com/svengreb/tmpl/releases/tag/v0.6.0
[gh-tmpl-rel-v0.7.0]: https://github.com/svengreb/tmpl/releases/tag/v0.7.0
[go-doc-mod]: https://golang.org/ref/mod
[npm-docs-cli-v7-ws]: https://docs.npmjs.com/cli/v7/using-npm/workspaces
[repo-compare-tag-v0.4.0_v0.5.0]: https://github.com/svengreb/tmpl-go/compare/v0.4.0...v0.5.0
[svengreb/tmpl#52]: https://github.com/svengreb/tmpl/issues/52
[tmpl#cicd]: https://github.com/svengreb/tmpl#cicd-action-workflow
[tmpl#node]: https://github.com/svengreb/tmpl#nodejs-yarn-and-npm
[yarn-docs-ws]: https://classic.yarnpkg.com/docs/workspaces
