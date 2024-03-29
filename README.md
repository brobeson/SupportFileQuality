# Support File Quality

[![Quality Control](https://github.com/brobeson/SupportFileQuality/actions/workflows/support_files.yaml/badge.svg)](https://github.com/brobeson/SupportFileQuality/actions/workflows/support_files.yaml)
[![GitHub Release](https://img.shields.io/github/v/release/brobeson/SupportFileQuality?sort=semver&logo=github&label=Release)](https://github.com/brobeson/SupportFileQuality/releases/latest)

This is a reusable workflow to ensure quality in project support files and tool configuration files (dot files).
For general help with reusable workflows, check out [GitHub's _Reusing workflows_ documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

## Getting Started

To use this workflow, just set it in the `uses` key of a job in your project's workflow file.
Here is an example workflow snippet that calls this workflow:

```yaml
jobs:
  dotFiles:
    name: Dot File Quality
    uses: brobeson/SupportFileQuality/.github/workflows/support_files.yaml@v1
```

## Steps

The workflow runs the steps described in the following sections.

1. **Spell Check**  
   The workflow runs [CSpell](https://cspell.org/) on all files in the repository except your _.git/_ directory.
   Use a [CSpell configuration](https://cspell.org/configuration/) in your repository to control the spell check behavior.
   You can add CSpell to your IDE to reduce the probability of this step finding errors.
   If you use [VS Code](https://code.visualstudio.com/), you can use the [Code Spell Checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker).
1. **Markdown Lint**  
   The workflow also runs [Markdownlint](https://github.com/DavidAnson/markdownlint) on all Markdown files in the repository.
   Use a [Markdownlint configuration](https://github.com/DavidAnson/markdownlint?tab=readme-ov-file#configuration) in your repository to control Markdownlint's behavior.
   If you use [VS Code](https://code.visualstudio.com/), you can use the [Markdownlint extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) to find mistakes as you edit your Markdown.
1. **Formatting**  
   Finally, the workflow runs [Prettier](https://prettier.io) on all Markdown, YAML, JSON, and TypeScript files in the repository.
   This does not attempt to modify any files.
   It just reports incorrectly formatted files.
