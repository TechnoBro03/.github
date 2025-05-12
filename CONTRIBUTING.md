# Table of Contents
- [Contributing Guide](#contributing-guide)
- [Code of Conduct](#code-of-conduct)
- [Question or Problem](#question-or-problem)
- [Found a Bug](#found-a-bug)
- [Missing a Feature](#missing-a-feature)
- [Submission Guidelines](#submission-guidelines)
	- [Submitting an Issue](#submitting-an-issue)
	- [Submitting a Pull Request](#submitting-a-pull-request-pr)
- [Branch Naming Conventions](#branch-naming-conventions)
- [Commit Message Conventions](#commit-message-conventions)
- [Coding Rules](#coding-rules)


# Contributing Guide

Thank you for considering a contribution! To keep collaboration smooth and inclusive, please follow these general guidelines:

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Question or Problem?

Please avoid opening GitHub issues for general support questions; reserve issues for bugs, features, or tasks.\
If you need help please visit the `Discussions` page on this repository.

## Found a Bug?

If you find a bug in the source code, you can help by [submitting an issue]().\
You can even [submit a Pull Request]() with a fix.

## Missing a Feature?

You can *request* a new feature by [submitting an issue](#submitting-an-issue).\
If you would like to *implement* a new feature, you can [submit a Pull Request]() directly.

## Submission Guidelines

### Submitting an Issue

Before submitting an issue, please search the issue tracker, an issue for your problem or request may already exist.

Use the issue templates to report bugs, request features, or log tasks. A good issue includes:

- A clear title and description
- Steps to reproduce (for bugs)
- Expected vs. actual behavior
- Any relevant version or environment info
- Suggested labels (e.g., `bug`, `feature`, `task`, `documentation`, `refactor`)

### Submitting a Pull Request (PR)

Before submitting a Pull Request, consider the following:

1. Search GitHub for an open or closed PR that relates to your submission. You don't want to duplicate effort.
1. Fork the repository.
1. Make your changes on a new branch following our [branch naming conventions](#branch-naming-conventions):
	```
	git checkout -b bug/123-my-fix main
	```
1. Follow the [Coding Rules]().
1. Commit your changes using our [commit message conventions](#commit-message-conventions).
1. Push your branch to GitHub:
	```
	git push origin bug/123-my-fix
	```
1. In GitHub, create a Pull Request to `main`.
	- In the description include:
		- What changed and why
		- Screenshots or demos (if applicable)
		- [References to related issues](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#referencing-issues-and-pull-requests)
	- If any changes are suggested then:
		- Make the required updates.
		- Ensure there are no additional issues after changes.
		- Rebase your branch and force push to your GitHub repository (this will update your Pull Request):
			```
			git rebase master -i
			git push -f
			```

You did it! Thank you for your contribution!

## Branch Naming Conventions

Create a branch per issue using: `{type}/{issue-number}-{optional-description}`

- **type**: `bug`, `feature`, `task`, or `issue`
- **issue-number**: GitHub issue number (omit `#`)
- **optional-description**: brief, hyphenated summary

**Example:** `feature/24-add-search-filter`

## Commit Message Conventions

Follow a structured format (similar to the [Angular Convention](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)):

```
<type>: <subject>

[optional body]

[optional footer(s)]
```

## Coding Rules

The keep the source code clear and consistent, please keep the following rules in mind:

- All features and bugs must be test before being integrated.
- Follow the pre-existing style in the project.