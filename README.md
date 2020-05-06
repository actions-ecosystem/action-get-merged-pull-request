# Action Get Merged Pull Request

[![actions-workflow-test][actions-workflow-test-badge]][actions-workflow-test]
[![release][release-badge]][release]
[![license][license-badge]][license]

This is a GitHub Action to get the pull request merged with the base branch.

This action supports `push` events with the base branch (e.g., `master`).

It would be more useful to use this with other GitHub Actions' outputs.

## Why this action?

The permissions for the GitHub token in forked repositories are read-only.
That's why it's necessary to trigger `push` events for base branch if you want to trigger `pull_request` `merged` events for some write use cases.

However, `push` events don't have information on pull requests, rather than `pull_request` events.
This action provides you with information on the pull request even if you trigger a `push` event.

The merged commit sha of the pull request fetched by this action is equivalent to the sha of the pushed commit.

For further details, see https://help.github.com/en/actions/reference/events-that-trigger-workflows#pull-request-events-for-forked-repositories.

## Inputs

|      NAME      |   DESCRIPTION   |   TYPE   | REQUIRED | DEFAULT |
|----------------|-----------------|----------|----------|---------|
| `github_token` | A GitHub token. | `string` | `true`   | `N/A`   |

## Outputs

|    NAME     |                                              DESCRIPTION                                               |   TYPE   |
| ----------- | ------------------------------------------------------------------------------------------------------ | -------- |
| `title`     | The title of the pull request.                                                                         | `string` |
| `body`      | The body of the pull request.                                                                          | `string` |
| `number`    | The number of the pull request.                                                                        | `number` |
| `labels`    | The list of labels for the pull request. Separated with line breaks if there're multiple labels.       | `string` |
| `assignees` | The list of assignees for the pull request. Separated with line breaks if there're multiple assignees. | `string` |

## License

Copyright 2020 The Actions Ecosystem Authors.

Action Get Merged Pull Request is released under the [Apache License 2.0](./LICENSE).

<!-- badge links -->

[actions-workflow-test]: https://github.com/actions-ecosystem/action-get-merged-pull-request/actions?query=workflow%3ATest
[actions-workflow-test-badge]: https://img.shields.io/github/workflow/status/actions-ecosystem/action-get-merged-pull-request/Test?label=Test&style=for-the-badge&logo=github

[release]: https://github.com/actions-ecosystem/action-get-merged-pull-request/releases
[release-badge]: https://img.shields.io/github/v/release/actions-ecosystem/action-get-merged-pull-request?style=for-the-badge&logo=github

[license]: LICENSE
[license-badge]: https://img.shields.io/github/license/actions-ecosystem/action-get-merged-pull-request?style=for-the-badge
