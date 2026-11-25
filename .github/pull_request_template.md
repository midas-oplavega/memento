## For the owner

<What the owner must decide or do, before or after the merge. "Nothing." if
nothing. Then the review line: the count of findings, the guidelines raised,
and, when the pull request has code, what the reviewer confirmed: the
planned tests present, the mutations caught out of those tried, the bug's
test failing on the base, and the tests checking behaviour.>

## What changed and why

<The change and the reason for it, for a reader who was not in the
conversation. In a project with districts, a pull request that touches more
than one says what changed district by district, then at the seams between
them.>

## Changelog

<The line this pull request adds under Unreleased in `CHANGELOG.md`, or
"None." when users and operators meet nothing new.>

## Decisions

<Choices this pull request makes that its issue did not settle: what was
decided, instead of what, and why. Leave the section out if there are none.>

## Verified

<The tests first: what each proves, and the IDs it proves when it proves
one; tests added beyond the plan, tests left to qualification, and waived
failures. Then the runs, their commands and the commit of the last one, and
the change's row of the core rules' Done table. Then what was not verified,
and why.>

Closes #<issue>, <a few words>

<`Closes` each issue it finishes, `Refs` each it advances. The last pull
request of a watched change says `Refs` for the change's issue, which stays
open while the feature is watched.>
