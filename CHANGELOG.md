<p align="center"><img src="https://raw.githubusercontent.com/svengreb/tmpl-go/main/assets/images/repository-hero.svg?sanitize=true"/></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/releases/latest" target="_blank" rel="noreferrer"><img src="https://img.shields.io/github/release/svengreb/tmpl-go.svg?style=flat-square&label=Release&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0"/></a></p>

<p align="center">Changelog of the <a href="https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository" target="_blank" rel="noreferrer">template repository</a> for Go projects.</p>

<!--lint disable no-duplicate-headings no-duplicate-headings-in-section-->

# 0.12.0

![Release Date: 2022-05-08](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2022-05-08&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.12.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.12.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/13)

⇅ [Show all commits][118]

## Improvements

<details>
<summary><strong>Update to <code>tmpl</code> template repository version <code>0.11.0</code></strong> — #91 ⇄ #92 (⊶ ff40ade4)</summary>

↠ Updated to [`tmpl` version `0.11.0`][119] which comes with…

1. [an opt-in Dependabot version update configuration][120] — this disabled the currently used [`.github/dependabot.yml` file][121] in order to remove the PR noise and reduce the maintenance overhead. Dependency updates will be made by keeping up-to-date with new `tmpl` repository versions instead which take care of this.

</details>

# 0.11.0

![Release Date: 2021-11-23](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2021-11-23&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.11.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.11.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/12)

⇅ [Show all commits][113]

## Improvements

<details>
<summary><strong>Disable revive linter rule <code>package-comments</code></strong> — #78 ⇄ #79 (⊶ 918ba3c8)</summary>

↠ Even though the [`package-comments` rule][117] of the [`revive` linter][87] is quite useful, it produces false-positive errors when another file already has a package documentation. Duplicating documentation is not a workaround so the rule has been disabled for now and might be re-enabled if the rule logic gets updated.

</details>

## Bug Fixes

<details>
<summary><strong><code>golangci-lint</code> fails to run due to <code>revive</code>s unknown <code>time-equal</code> rule</strong> — #76 ⇄ #77 (⊶ ab326723)</summary>

↠ The [`time-equal` rule][115] was added in #64, but the [`revive` linter][87] used by `golangci-lint` does not yet include the rule in the [current release version][114] but only merged it into the `main` branch. Therefore linting failed because the rule is not known (yet) and `golangci-lint` exits before running any linter.
To fix the problem the `time-equal` rule has been disabled again for now and will be enabled again when it is available in a new `revive` version that is used by `golangci-lint`.

</details>

# 0.10.0

![Release Date: 2021-11-21](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2021-11-21&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.10.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.10.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/11)

⇅ [Show all commits][105]

## Improvements

<details>
<summary><strong>Disable <code>golangci-lint</code>'s default excluded issues</code></strong> — #72 ⇄ #73 (⊶ c099c6ee)</summary>

↠ By default [golangci-lint][3] [excludes specific issues][107] (matches) that are known to be "annoying", but this also includes issues explicitly enabled by this template, e.g. the [revive][87] rule to [check that exported function and methods always have a comment][109].
To prevent these issues to be found the default excludes will be disables through the `issues.exclude-use-default` configuration field.

</details>

<details>
<summary><strong>Cache Go dependencies and build outputs in <code>ci-go</code> workflow</code></strong> — #74 ⇄ #75 (⊶ 05c0d385)</summary>

↠ To improve workflow execution time for the [`ci-go` workflow][110] the [`actions/cache`][111] GitHub action is now used to cache Go dependencies and build outputs. Also see the detailed [documentation about “Caching dependencies to speed up workflows“][112] to learn more about the way `action/cache` works.

</details>

# 0.9.0

![Release Date: 2021-11-20](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2021-11-20&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.9.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.9.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/10)

⇅ [Show all commits][104]

## Improvements

<details>
<summary><strong>Update to <code>golangci-lint</code> version <code>1.43.0</code></strong> — #64 ⇄ #65 (⊶ 55945b16)</summary>

↠ The currently latest [`golangci-lint` version 1.43.0][78] introduced new linters and updated supported ones:

1. [tagliatelle][68] ([v1.40.0][69]) — Handles `struct` tags name casing.
   This linter is **disabled by default**, but will be **enabled** for this template to improve consistency across tag names.
2. [errorlint][1] ([v1.40.0][69]) — This linter has been disabled in #39 due to prevent false-positive errors, but will be **enabled** again with the newly introduced [`errorf` option][71] being disabled to prevent this from happening again while still taking advantage of the `assert` and `comparison` checks.
3. [wrapcheck][2] ([v1.40.0][69]) — This linter is known to cause false-positive errors for the main module (`go list -m`) of the repository where `golangic-lint` is being run, but in [version `2.3.0`][73] the `ignorePackageGlobs` option was added that allows to ignore packages by pattern. Therefore in each project the main module should be added as wildcard. Also see [tomarrell/wrapcheck#2][74] for details and discussions about this known problem.
4. [golint][75] ([v1.40.1][76]) — Remove deprecated linter.
   4.1 The recommended drop-in replacement is [revive][87] which is **disabled by default**, but will be **enabled** for this template.
5. [gofumpt][83] ([v1.42.0][82]) — Add the `lang-version` with value set to `1.17` to target the (currently) latest Go version.
6. [bidichk][77] ([v1.43.0][78]) — Checks for dangerous unicode character sequences.
   This linter is **disabled by default**, but will be **enabled** for this template to prevent "trojan source" bugs.
7. [nilnil][79] ([v1.43.0][78]) — Checks that there is no simultaneous return of `nil` error and an invalid value.
   This linter is **disabled by default**, but will be **enabled** for this template to prevent ambiguous returns.
8. [tenv][80] ([v1.43.0][78]) — Detects using `os.Setenv` instead of `t.Setenv` since Go 1.17.
   This linter is **disabled by default**, but will be **enabled** for this template to prevent errors in tests.
9. [contextcheck][81] ([v1.43.0][78]) — Checks if functions whether use a non-inherited context.
   This linter is **disabled by default**, but will be **enabled** for this template to broken call chains and loss of context information.
10. [lll][84] — Add the `tab-width` option with value set to `2` to use two spaces for the width of one tab.
11. [gci][85] — Add the comma-separated [list of prefixes for local package imports][86] to be put after 3rd-party packages.

</details>

<details>
<summary><strong>Update Go module to Go <code>1.17</code></strong> — #66 ⇄ #67 (⊶ c20ba3bd)</summary>

↠ Before the [Go module][88] used Go version `1.16` so it has been updated to the [currently latest minor version `1.17`][89].

</details>

<details>
<summary><strong>Optimized GitHub action workflows for Go and Node</strong> — #68 ⇄ #69 (⊶ c3ff68b5)</summary>

↠ Before all jobs were summarized in the [`ci` workflow][90] but not separated by their scope, i.e. Go and Node specific tasks. The workflow was also not optimized to only run when specific files have been changed which resulted in false-positive executions and wasted limited free tier and developer time.
Therefore the `ci` workflow has been optimized by splitting it into new `ci-go` and `ci-node` workflows.

## CI Go

The new `ci-go` workflow…

- only runs when any `*.go` file has been modified. See the extensive [GitHub action documentations about `on.<push|pull_request>.paths`][93] and the [filter pattern cheat sheet][94] for more details.
- only runs for `ubuntu-latest` instead of a matrix with `macos-latest` and `windows-latest` which should be added for projects with platform specific code.

## CI Node

The new `ci-node` workflow…

- only runs when any `*.js`, `*.json`, `*.md`, `*.yaml` and `*.yml` file has been modified. This matches the [lint-staged][91], Prettier and remark configurations. See the extensive [GitHub action documentations about `on.<push|pull_request>.paths`][93] and the [filter pattern cheat sheet][94] for more details.
- only runs for `ubuntu-latest` instead of a matrix with `macos-latest` and `windows-latest` which should be added for projects with platform specific code.
- uses cache `npm` dependencies which is [possible as of `actions/setup-node@v2.2.0`][92].

## Silent linting errors for CI/CD environments

When running the [configured linting tasks][95] the [Prettier CLI][96] prints matches to the standard output with a visual preview of the file content and a marker at the specific element. When files that store secret data, e.g. when [encrypted with `git-crypt`][97], are [decrypted in the GitHub Actions][98] this could leak this data when Prettier finds errors in these files.
To prevent these case new CI specific linting tasks have been added with a [`silent` `loglevel`][99]. This however comes with the drawback that possible linting errors must be analyzed locally, but the code quality is still ensured by blocking subsequent workflows.

</details>

<details>
<summary><strong>Update to tmpl template repository version <code>0.10.0</code></strong> — #70 ⇄ #71 (⊶ 670859ea)</summary>

↠ Updated to [`tmpl` version `0.10.0`][100] which comes with…

1. [an optimized GitHub action workflow scope][101] — this change has also already been resolved in #68, but additionally created the `ci-go` GitHub Action workflow.
2. [the regular Node package dependency & GitHub action version updates][102]
3. [the migration to the Markdown style guide version `0.4.0`][103]

</details>

# 0.8.0

![Release Date: 2021-04-27](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2021-04-27&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.8.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.8.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/9)

⇅ [Show all commits][54]

## Improvements

<details>
<summary><strong>Update to golangci-lint <code>`v1.39.x</code></strong> — #56 ⇄ #57 (⊶ 3e60efbc)</summary>

↠ [`golangci-lint` version 1.39.0][57] introduced new linters and updated supported ones:

1. [predeclared][63] ([v1.35.0][55]) — Checks for definitions and declarations that shadows one of [Go's pre-declared identifiers][67].
   This linter is **disabled by default**, but will be **enabled** for this template to help to prevent shadowed identifiers.
2. [interfacer][62] ([v1.38.0][56]) — [Has been deprecated][58] and will be removed from the enabled linter in this template.
3. [scopelint][61] ([v1.39.0][57]) — [Has been deprecated][59] and will be replaced by [exportloopref][60].
   The `exportloopref` linter is **disabled by default**, but will be **enabled** for this template to help to catch loop variable bugs.

</details>

<details>
<summary><strong>Update to <code>tmpl</code> template repository version <code>0.9.0</code></strong> — #58 ⇄ #59 (⊶ 5f0b1cf0)</summary>

↠ Updated to [`tmpl` version `0.9.0`][64] which [moves from Yarn back to npm again][66], [improves and clarifies the handling of lockfiles][65] and comes with some major Node package dependency & GitHub action version updates.

</details>

# 0.7.0

![Release Date: 2021-04-21](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2021-04-21&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.7.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.7.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/8)

⇅ [Show all commits][49]

## Improvements

<details>
<summary><strong>Updated to Go 1.16</strong> — #54 ⇄ #55 (⊶ 1f20fe12)</summary>

↠ [Go 1.16][53] is finally released so the Go version used for the `actions/setup-go` action in the `ci` workflow has been updated from `1.15.x` to `1.16.x` and the defined Go version in the `go.mod` file bumped to `go 1.16`.

</details>

## Tasks

<details>
<summary><strong>Node.js package dependency & GitHub action version updates</strong> — #42, #47</summary>

↠ Bumped outdated Node.js package dependencies and GitHub actions to their latest versions:

- #48, #52 (⊶ e2487f2b, c13b8122) [`actions/setup-node`][36] from [v2.1.3 to v2.1.5][48]
- #49 (⊶ 9250ff93) [`github.com/stretchr/testify`][52] from [v1.6.1 to v1.7.0][51]
- #50, #51, #53 (⊶ bd642b5c, ba39b7e1, f208cdcc) [`golangci/golangci-lint-action`][6] from [v2 to v2.5.2][50]

</details>

# 0.6.0

![Release Date: 2020-12-12](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-12-12&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.6.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.6.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/7)

⇅ [Show all commits][38]

## Improvements

<details>
<summary><strong>Renamed <code>/app</code> to <code>/apps</code></strong> — #37 ⇄ #38 (⊶ 5551df2f)</summary>

↠ Using the majority `apps` as name for the [`/app` directory][44] conveys a better understanding of the actual use case and makes it more clear that it can contain more than one application in the [monorepo][47] layout.
This also aligns with the [example in the `/web` directory documentation][45] and the Yarn/NPM [workspace configuration in the `package.json` file][37] where both using the `apps` directory.

</details>

<details>
<summary><strong>Disabled <code>errorlint</code> to prevent false-positive errors</strong> — #39 ⇄ #40 (⊶ 28f888a2)</summary>

↠ In #21 `golangci-lint` was updated to the [currently latest version 1.32.0][9] which introduced the [errorlint][1] that has been enabled for this template repository. As it turns out it causes a lot of false-positives errors for code lines that explicitly do not wrap the error to prevent it become part of the public API.
Therefore the linter has been disabled again because the update also introduced the new [wrapcheck][2] linter which helps to prevent that errors from external packages are exposed to the public API.

</details>

<details>
<summary><strong>Update to “tmpl“ template repository version 0.8.0</strong> — #45 ⇄ #46 (⊶ 39cf0b85)</summary>

↠ Updated to [“tmpl“ version 0.8.0][42] which [reduces _Dependabot_ PR noise for the NPM package ecosystem][43].

</details>

## Tasks

<details>
<summary><strong>Prepared project/repository publication</strong> — #35 ⇄ #36 (⊶ 0aec1aef)</summary>

↠ Before switching the [GitHub repository visibility][39] to “public“ a few adjustments had to be made.
Basically #22 was reverted, taking the changes from #23 into account, so that SVG images like the repository hero are using the URLs for public repositories again instead of the ones that allow to resolve the files in private repositories.

</details>

<details>
<summary><strong>Node.js package dependency & GitHub action version updates</strong> — #42, #47</summary>

↠ Bumped outdated Node.js package dependencies and GitHub actions to their latest versions:

- #42 (⊶ 6e91700f) [`prettier`][41] from [2.1.2 to 2.2.1][40] — The the [official Prettier 2.2 introduction blog post][46] for more details.
- #47 (⊶ 90c22f24) [`actions/setup-node`][36] from [v2.1.2 to v2.1.3][35]

</details>

# 0.5.0

![Release Date: 2020-11-10](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-11-10&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.5.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.5.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/6)

⇅ [Show all commits][26]

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
The `package.json` file has also been extended to include the [Yarn][34]/[NPM][30] `workspaces` field.

</details>

<details>
<summary><strong>Update to <code>tmpl</code> template repository version 0.7.0</strong> — #24, #33 ⇄ #25, #34 (⊶ 793efc26, 81385803)</summary>

↠ Updated to [`tmpl` version 0.7.0][28] (including version [0.6.0][27]) which introduced a configuration for [automated dependency updates and security alerts][31] with [Dependabot][7]. Next to the included update configurations for the [CI/CD GitHub action workflow][32] and [Yarn/NPM dependencies][33], the file has been extended to support [Go modules][29].
This version also updated to the latest Node.js package dependency & GitHub Action versions.

</details>

# 0.4.0

![Release Date: 2020-10-31](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-10-31&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.4.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.4.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/5)

⇅ [Show all commits][22]

## Features

<details>
<summary><strong>Update to golangci-lint version 1.32.0</strong> — #20 ⇄ #21 (⊶ 072aad99)</summary>

↠ The currently latest [`golangci-lint` version 1.32.0][9] introduced new linters that have been configured for this template repository:

1. [wrapcheck][2] — Checks that errors returned from external packages are wrapped.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help tp reduce error context loss.
2. [errorlint][1] — Helps to make more efficient use of the error wrapping scheme introduced in Go 1.13.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help to use Go's new error handling concept.
3. [tparallel][5] — Detects inappropriate usage of `t.Parallel()` method in Go tests.
   This linter is **disabled by default**, but has been **enabled** for this template repository to help to prevent parallelism errors in tests.

</details>

<details>
<summary><strong>Update to "tmpl" template repository version 0.5.0</strong> — #22 ⇄ #23 (⊶ 5da341c3)</summary>

↠ Updated to ["tmpl" version 0.5.0][23] which now uses a [namespace for the NPM package name][25] that helps to prevent collisions with already existing NPM packages like [tmpl][24].

</details>

# 0.3.0

![Release Date: 2020-09-25](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-25&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.3.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.3.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/4)

⇅ [Show all commits][20]

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

- The `lint-go` job has been changed to only run on the [currently latest stable Go version `1.15.x`][10] only on _Linux_ because `golangci-lint` doesn't care about the _Go_ version and OS it runs on but only statically checks the source code.
- The `test` job has been changed to only run on the [currently latest stable Go version `1.15.x`][10].

These changes help to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary tasks.

</details>

<details>
<summary><strong>Adapt CI workflow "on" run configurations from "tmpl" template repository</strong> — #18 ⇄ #19 (⊶ ec1539cd)</summary>

↠ Before the CI workflow only used the `push` configuration for the `on` field. To improve the performance a more fine grained configuration is now used that has already been defined in [the "tmpl" template repository][8]:

- Only runs on pushes to the `main` branch.
- Only runs on pushes for `v*` tags.
- Always runs for pushes to PRs.

These changes help to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary runs.

</details>

## Tasks

<details>
<summary><strong>Adapt to "tmpl" template repository version 0.4.0</strong> — #14 ⇄ #15 (⊶ 9d50ec0e)</summary>

↠ Adapted to ["tmpl" version 0.4.0][19] which includes a [optimized OS version matrix strategy for Node based tasks in the CI workflow][21] that helps to keep the required GitHub Action run minutes for the account of this repository as small as possible without wasting resources for unnecessary tasks.

</details>

# 0.2.0

![Release Date: 2020-09-24](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-24&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.2.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.2.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/3)

⇅ [Show all commits][18]

## Features

<details>
<summary><strong>Basic testing in CI workflow</strong> — #10 ⇄ #11 (⊶ f65759e6)</summary>

↠ Before the CI workflow only ran _Node_ and _Go_ based linters, but doesn't took _Go_ tests into account. This has been changed by adding a new job to run tests with _Go_'s official `go test` command with enabled coverage and race detector.

</details>

# 0.1.1

![Release Date: 2020-09-21](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-21&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.1.1&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.1.1&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/2)

⇅ [Show all commits][15]

## Bug Fixes

<details>
<summary><strong>YAML multiline string without "block chomping" for config go-header linter causes golangci-lint to fail</strong> — #6 ⇄ #7 (⊶ 910c06ff)</summary>

↠ The configuration of the [go-header][4] linter is defined in the [golangci-lint][3] YAML configuration, but the [YAML multiline-string][16] doesn't used ["block chomping][17] which resulted in a final newline at the end of the template.
This caused golangci-lint to fail because the configured template content doesn't match the parsed text.
To fix this problem the YAML _block chomping_ syntax is now used for the multiline-string so that the final newline at the end gets stripped.

</details>

<details>
<summary><strong>Invalid branch & CI workflow name in README badges </strong> — #8 ⇄ #9 (⊶ e138ca15)</summary>

↠ The name of the branch for the badge URL of the repository changelog was `master` instead of `main` and the GitHub CI action workflow used the uppercase name `CI` instead of `ci`.

</details>

# 0.1.0

![Release Date: 2020-09-20](https://img.shields.io/static/v1?style=flat-square&label=Release%20Date&message=2020-09-20&colorA=4c566a&colorB=88c0d0) [![Project Board](https://img.shields.io/static/v1?style=flat-square&label=Project%20Board&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/users/svengreb/projects/4/views/3) [![Milestone](https://img.shields.io/static/v1?style=flat-square&label=Milestone&message=0.1.0&logo=github&logoColor=eceff4&colorA=4c566a&colorB=88c0d0)](https://github.com/svengreb/tmpl-go/milestone/1)

⇅ [Show all commits][14]

This is the initial release version of _tmpl-go_.
The basic project setup, structure and development workflow has been bootstrapped by [the base _tmpl_ template repository][8].
The additional Go specific initial configurations and documentations are covered in the following sections of this version changelog to introduce used technologies and explain why several decisions have been made.

## Features

<details>
<summary><strong>Bootstrap from "tmpl" base template repository</strong> — #1 (⊶ 87400d37)</summary>

<p align="center"><img src="https://github.com/svengreb/tmpl/blob/main/assets/images/repository-hero-base.svg?raw=true"/></p>

↠ Bootstrapped the basic project setup, structure and development workflow [from version 0.3.0][12] of the [base "tmpl" template repository][8].
Additionally specific assets like the repository hero image were also added.

</details>

<details>
<summary><strong>Go Module</strong> — #1 ⇄ #3 (⊶ 52bea37b)</summary>

↠ tmpl-go uses the currently latest Go version [1.15.0][10] with [Go Modules][11] and `github.com/svengreb/tmpl-go` as module name.

</details>

<details>
<summary><strong>Code quality with "golangci-lint"</strong> — #4 ⇄ #5 (⊶ b20e205f)</summary>

↠ To ensure a good code quality the Go ecosystem has hundreds of linters, each with a different purpose. Instead of installing and running multiple linters separately [golangci-lint][3] provides a uniform interface to run most popular and useful linters in parallel and with many additional configuration features.
The actual runner is open source and can be used locally as well in any private CI/CD pipeline. In order to use it for tmpl-go, a `.golangci.yml` configuration file has been added.

The runner is used in the [the existing _CI_ GitHub action workflow][13] through the [gh-golangci/golangci-lint-action][6] GitHub action that has been created by the golangci-lint maintainers.

</details>

<p align="center">Copyright &copy; 2020-present <a href="https://www.svengreb.de" target="_blank" rel="noreferrer">Sven Greb</a></p>

<p align="center"><a href="https://github.com/svengreb/tmpl-go/blob/main/LICENSE" target="_blank" rel="noreferrer"><img src="https://img.shields.io/static/v1.svg?style=flat-square&label=License&message=MIT&logoColor=eceff4&logo=github&colorA=4c566a&colorB=88c0d0"/></a></p>

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

[1]: https://github.com/polyfloyd/go-errorlint
[2]: https://github.com/tomarrell/wrapcheck
[3]: https://golangci-lint.run
[6]: https://github.com/golangci/golangci-lint-action
[8]: https://github.com/svengreb/tmpl

<!-- Shared Links -->

[9]: https://github.com/golangci/golangci-lint/releases/tag/v1.32.0
[10]: https://golang.org/doc/go1.15
[87]: https://github.com/mgechev/revive

<!-- v0.1.0 -->

[11]: https://github.com/golang/go/wiki/Modules
[12]: https://github.com/svengreb/tmpl/releases/tag/v0.3.0
[13]: https://github.com/svengreb/tmpl-go/actions?query=workflow%3ACI
[14]: https://github.com/svengreb/tmpl-go/compare/87400d37...v0.1.0

<!-- v0.1.1 -->

[4]: https://github.com/denis-tingajkin/go-header
[15]: https://github.com/svengreb/tmpl-go/compare/v0.1.0...v0.1.1
[16]: https://yaml-multiline.info
[17]: https://yaml.org/spec/1.2/spec.html#id2794534

<!-- v0.2.0 -->

[18]: https://github.com/svengreb/tmpl-go/compare/v0.1.1...v0.2.0

<!-- v0.3.0 -->

[19]: https://github.com/svengreb/tmpl/releases/tag/v0.4.0
[20]: https://github.com/svengreb/tmpl-go/compare/v0.2.0...v0.3.0
[21]: https://github.com/svengreb/tmpl/issues/46

<!-- v0.4.0 -->

[22]: https://github.com/svengreb/tmpl-go/compare/v0.3.0...v0.4.0
[23]: https://github.com/svengreb/tmpl/releases/tag/v0.5.0
[24]: https://www.npmjs.com/package/tmpl
[25]: https://github.com/svengreb/tmpl/issues/48
[5]: https://github.com/moricho/tparallel

<!-- v0.5.0 -->

[7]: https://dependabot.com
[26]: https://github.com/svengreb/tmpl-go/compare/v0.4.0...v0.5.0
[27]: https://github.com/svengreb/tmpl/releases/tag/v0.6.0
[28]: https://github.com/svengreb/tmpl/releases/tag/v0.7.0
[29]: https://golang.org/ref/mod
[30]: https://docs.npmjs.com/cli/v7/using-npm/workspaces
[31]: https://github.com/svengreb/tmpl/issues/52
[32]: https://github.com/svengreb/tmpl#cicd-action-workflow
[33]: https://github.com/svengreb/tmpl#nodejs-yarn-and-npm
[34]: https://classic.yarnpkg.com/docs/workspaces

<!-- v0.6.0 -->

[35]: https://github.com/actions/setup-node/compare/v2.1.2...27082cecf3ff7a1742dbd5e12605f0cb59dce2d9
[36]: https://github.com/actions/setup-node
[37]: https://github.com/svengreb/tmpl-go/blob/main/package.json#L24
[38]: https://github.com/svengreb/tmpl-go/compare/v0.5.0...v0.6.0
[39]: https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/setting-repository-visibility
[40]: https://github.com/prettier/prettier/compare/2.1.2...2.2.1
[41]: https://github.com/prettier/prettier
[42]: https://github.com/svengreb/tmpl/releases/tag/v0.8.0
[43]: https://github.com/svengreb/tmpl/issues/65
[44]: https://github.com/svengreb/tmpl-go/tree/main/app
[45]: https://github.com/svengreb/tmpl-go/tree/main/web#example
[46]: https://prettier.io/blog/2020/11/20/2.2.0.html
[47]: https://trunkbaseddevelopment.com/monorepos

<!-- v0.7.0 -->

[48]: https://github.com/actions/setup-node/compare/v2.1.3...v2.1.5
[49]: https://github.com/svengreb/tmpl-go/compare/v0.6.0...v0.7.0
[50]: https://github.com/golangci/golangci-lint-action/compare/v2...v2.5.2
[51]: https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0
[52]: https://github.com/stretchr/testify
[53]: https://golang.org/doc/go1.16

<!-- v0.8.0 -->

[54]: https://github.com/svengreb/tmpl-go/compare/v0.7.0...v0.8.0
[55]: https://github.com/golangci/golangci-lint/releases/tag/v1.35.0
[56]: https://github.com/golangci/golangci-lint/releases/tag/v1.38.0
[57]: https://github.com/golangci/golangci-lint/releases/tag/v1.39.0
[58]: https://github.com/golangci/golangci-lint/pull/1755
[59]: https://github.com/golangci/golangci-lint/pull/1819
[60]: https://github.com/kyoh86/exportloopref
[61]: https://github.com/kyoh86/scopelint
[62]: https://github.com/mvdan/interfacer
[63]: https://github.com/nishanths/predeclared
[64]: https://github.com/svengreb/tmpl/releases/tag/v0.9.0
[65]: https://github.com/svengreb/tmpl/issues/70
[66]: https://github.com/svengreb/tmpl/issues/72
[67]: https://golang.org/ref/spec#Predeclared_identifiers

<!-- v0.9.0 -->

[68]: https://github.com/ldez/tagliatelle
[69]: https://github.com/golangci/golangci-lint/releases/tag/v1.40.0
[71]: https://golangci-lint.run/usage/linters/#errorlint
[73]: https://github.com/tomarrell/wrapcheck/releases/tag/v2.3.0
[74]: https://github.com/tomarrell/wrapcheck/issues/2
[75]: https://github.com/golang/lint
[76]: https://github.com/golangci/golangci-lint/releases/tag/v1.40.1
[77]: https://github.com/breml/bidichk
[78]: https://github.com/golangci/golangci-lint/releases/tag/v1.43.0
[79]: https://github.com/Antonboom/nilnil
[80]: https://github.com/sivchari/tenv
[81]: https://github.com/sylvia7788/contextcheck
[82]: https://github.com/golangci/golangci-lint/releases/tag/v1.42.0
[83]: https://github.com/mvdan/gofumpt
[84]: https://github.com/walle/lll
[85]: https://github.com/daixiang0/gci
[86]: https://golangci-lint.run/usage/linters/#gci
[88]: https://github.com/svengreb/tmpl-go/blob/97fdc142/go.mod
[89]: https://golang.org/doc/go1.17
[90]: https://github.com/svengreb/tmpl-go/blob/c20ba3bd/.github/workflows/ci.yml
[91]: https://github.com/svengreb/tmpl-go/blob/c20ba3bd/lint-staged.config.js#L12
[92]: https://github.com/actions/setup-node/releases/tag/v2.2.0
[93]: https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#onpushpull_requestpaths
[94]: https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet
[95]: https://github.com/svengreb/tmpl-go/blob/c20ba3bd/package.json#L28
[96]: https://prettier.io/docs/en/cli.html
[97]: https://github.com/svengreb/antarctica/issues/170
[98]: https://github.com/svengreb/antarctica/blob/0e6abe44/.github/workflows/ci-go.yaml#L29-L32
[99]: https://prettier.io/docs/en/cli.html#--loglevel
[100]: https://github.com/svengreb/tmpl/releases/tag/v0.10.0
[101]: https://github.com/svengreb/tmpl/issues/84
[102]: https://github.com/svengreb/tmpl/issues/86
[103]: https://github.com/svengreb/tmpl/issues/76
[104]: https://github.com/svengreb/tmpl-go/compare/v0.8.0...v0.9.0

<!-- v0.10.0 -->

[105]: https://github.com/svengreb/tmpl-go/compare/v0.9.0...v0.10.0
[107]: https://golangci-lint.run/usage/configuration/#config-file
[109]: https://github.com/mgechev/revive/blob/master/RULES_DESCRIPTIONS.md#exported
[110]: https://github.com/svengreb/tmpl-go/blob/c099c6ee246eb402b63f7a605ca647c481a02eab/.github/workflows/ci-go.yaml
[111]: https://github.com/actions/cache
[112]: https://docs.github.com/en/actions/advanced-guides/caching-dependencies-to-speed-up-workflows

<!-- v0.11.0 -->

[113]: https://github.com/svengreb/tmpl-go/compare/v0.10.0...v0.11.0
[114]: https://github.com/mgechev/revive/releases/tag/v1.1.2
[115]: https://github.com/mgechev/revive/blob/master/RULES_DESCRIPTIONS.md#time-equal
[117]: https://github.com/mgechev/revive/blob/master/RULES_DESCRIPTIONS.md#package-comments

<!-- v0.12.0 -->

[118]: https://github.com/svengreb/tmpl-go/compare/v0.11.0...v0.12.0
[119]: https://github.com/svengreb/tmpl/releases/tag/v0.11.0
[120]: https://github.com/svengreb/tmpl/issues/94
[121]: https://github.com/svengreb/tmpl-go/blob/39cf0b85/.github/dependabot.yml
