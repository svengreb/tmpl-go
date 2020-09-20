<p align="center"><img src="https://github.com/svengreb/tmpl-go/blob/main/assets/images/repository-hero.svg?raw=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/releases/latest"><img src="https://img.shields.io/github/release/svengreb/tmpl-go.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center">Changelog of the <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank">repository template</a> for Go projects.</p>

<!--lint disable no-duplicate-headings no-duplicate-headings-in-section-->

# 0.1.0

![Release Date: 2020-09-20](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-08-26&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/projects/4) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/1)

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

<!-- v0.1.0 -->

[gh-go-wiki-modules]: https://github.com/golang/go/wiki/Modules
[gh-tmpl-release-v0.3.0]: https://github.com/svengreb/tmpl/releases/tag/v0.3.0
[gh-tmpl]: https://github.com/svengreb/tmpl
[go-rln-1.15.0]: https://golang.org/doc/go1.15
[golangci-lint-action]: https://github.com/golangci/golangci-lint-action
[golangci-lint]: https://github.com/golangci/golangci-lint
[repo-action-query-ci]: https://github.com/svengreb/tmpl-go/actions?query=workflow%3ACI
[repo-compare-tag-init_v0.1.0]: https://github.com/svengreb/tmpl-go/compare/87400d37...v0.1.0
