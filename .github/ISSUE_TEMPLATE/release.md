---
name: Release
about: A release or a hotfix, with the go or no-go note the owner decides on at gate 4
---

## Go or no-go

<Written once the release is qualified, with the `releasing` skill. The
owner's go is a comment on this issue, and covers exactly the actions
listed here.

- **Version:** <vX.Y.Z>, from commit <commit>, build <where it is kept>.
- **Go or no-go:** <which, and what blocks, if anything>.
- **Risks to accept:** <each>, or none.
- **Not verified:** <each, with why>, or none.
- **A release candidate:** <where it ran, for how long, and its result>,
  or none.
- **The build's files:** <for a build that is published, checked for
  secrets and private data, and the result>, or none.
- **Rules read again:** <each sector rule governing a part this release
  changes, with its date>, or none.
- **The go covers:** <each action on production, in order: the tag, the
  backup, the migrations, each store form brought in line, the deploy or
  the publish, and the check after it>.
- **The way back:** <the rollback, a restore of the backup, or yanking and
  fixing forward>, and what triggers it. A first release says what the way
  back is instead.
- **1.0.0:** <before 1.0.0, once the product is used in production: whether
  this release should be 1.0.0>.>

## What is in it

<A link to the changelog pull request. For a hotfix, the fix's pull request,
and its carry to the release branch when it has one.>

## Qualification

<A link to the qualification report, from the `qualifying-a-change` skill.>
