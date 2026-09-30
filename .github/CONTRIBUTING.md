# Contribution Guidelines

Please ensure your pull request adheres to the following guidelines:

- Please search previous suggestions before making a new one, as yours
  may be a duplicate.

- Please make an individual pull request for each suggestion.

- Use the following format: \[RESOURCE\](WEB-LINK) - DESCRIPTION.

- Keep descriptions short and simple.

- End all descriptions with a full stop/period.

- Make sure your text editor is set to remove trailing whitespace.

- Order projects alphabetically within each category.

- Check your spelling and grammar.

- New categories, or improvements to the existing categorisation are
  welcome.

## Pull Requests Workflow

Please, submit one pull requests with one link per PR. If you want to
add several links, you should create PR for each links, unless all of
the proposed projects are belong to the same category. Pull request
should have meaningful description what this project do, why do you want
to add it to the list and any other info which might be useful. This
will help maintainers with the review process.

## Quality standard

To stay on the list, projects should follow these quality standards:

- Generally useful to the community

- Actively maintained (even if that just means acknowledging open issues
  when they arise)

- Stable

- Documented

- Tests

- For GitHub repositories, we currently have a soft limit of no less
  than 50 stars

Thank you for your suggestions!

## Scripts

This repository includes a couple of scripts to help with the project
maintaining.

- `scripts/update-toc.fsx`: run this one manually when you need to
  rebuild the table of contents.

- `scripts/check-dead-links.fsx`: this script runs on CI to ensure we
  have no dead links in our list.

## Signed commits

Every commit that reaches the default branch must be signed; a ruleset refuses
unsigned pushes. Estate policy:
[SIGNING-POLICY](https://github.com/hyperpolymath/standards/blob/main/docs/SIGNING-POLICY.adoc).

- **People and interactive agents** sign with an SSH key registered on GitHub
  as a *signing* key (`gpg.format=ssh`, `user.signingkey=<key>.pub`,
  `commit.gpgsign=true`). The committer email must be verified on that account.
- **Apps, bots and workflows** never `git push` local commits. They write
  through the API (`createCommitOnBranch` or the estate `signed-push` action)
  so that GitHub signs each commit.
- Merge PRs with **squash**. The ruleset checks every commit on the PR branch,
  not just the result, so one unsigned commit blocks the merge. Re-create such a
  branch with signed commits (`git cherry-pick -S`) and open a new PR.
  Rebase-merge replays commits unsigned and is disabled.
