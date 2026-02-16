# Support File Quality

[![Workflow Quality](https://github.com/brobeson/SupportFileQuality/actions/workflows/support_files.yaml/badge.svg)](https://github.com/brobeson/SupportFileQuality/actions/workflows/support_files.yaml)
[![GitHub Release](https://img.shields.io/github/v/release/brobeson/SupportFileQuality?sort=semver&logo=github&label=Release)](https://github.com/brobeson/SupportFileQuality/releases/latest)

This is a reusable workflow to ensure quality in project support files and tool configuration files (dot files).
For general help with reusable workflows, check out [GitHub's _Reusing workflows_ documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

## Getting Started

To use this workflow, just set it in the `uses` key of a job in your project's workflow file.
Here is an example workflow snippet that calls this workflow:

```yaml
jobs:
  projectFiles:
    name: Project File Quality
    uses: brobeson/SupportFileQuality/.github/workflows/support_files.yaml@v1
```

## Steps

The workflow runs the following steps.

1. **Spell Check**  
   The workflow runs [CSpell](https://cspell.org/) on all files in the repository.
   Use a [CSpell configuration](https://cspell.org/configuration/) in your repository to control the spell check behavior.
   You can add CSpell to your IDE to reduce the probability of this step finding errors.
   If you use [VS Code](https://code.visualstudio.com/), you can use the [Code Spell Checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker).
1. **Markdown Lint**  
   The workflow also runs [Markdownlint](https://github.com/DavidAnson/markdownlint) on all Markdown files in the repository.
   It uses [markdownlint-cli2](https://github.com/DavidAnson/markdownlint-cli2), so you can [configure it](https://github.com/DavidAnson/markdownlint-cli2#configuration).
1. **Prettier**  
   Finally, the workflow runs [Prettier](https://prettier.io/) to check formatting of any files in the repository.
   It does _not_ format and commit changes; it reports files that are incorrectly formatted.

## Issue Tracking

[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/SupportFileQuality/bug?logo=github&label=Bugs)](https://github.com/brobeson/SupportFileQuality/issues?q=is%3Aissue+is%3Aopen+label%3Abug)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/SupportFileQuality/enhancement?logo=github&label=Enhancements)](https://github.com/brobeson/SupportFileQuality/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement)
[![GitHub Issues or Pull Requests by label](https://img.shields.io/github/issues/brobeson/SupportFileQuality/new%20step?logo=github&label=New%20Steps)](https://github.com/brobeson/SupportFileQuality/issues?q=is%3Aopen+is%3Aissue+label%3A%22new+step%22)
[![GitHub milestone details](https://img.shields.io/github/milestones/progress/brobeson/SupportFileQuality/1?logo=github)](https://github.com/brobeson/SupportFileQuality/milestone/1)

[Report a bug](https://github.com/brobeson/SupportFileQuality/issues/new?assignees=brobeson&labels=bug&projects=&template=bug.yaml) |
[Request a new step](https://github.com/brobeson/SupportFileQuality/issues/new?assignees=brobeson&labels=new+step&projects=&template=new_step.yaml) |
[Update an existing step](https://github.com/brobeson/SupportFileQuality/issues/new?assignees=brobeson&labels=enhancement&projects=&template=enhancement.yaml)
