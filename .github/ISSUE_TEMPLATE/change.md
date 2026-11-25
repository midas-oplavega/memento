---
name: Change
about: A change to make, with why, its requirements, its size and its approach
---

## Why

<Medium and large: what is gained or lost, for whom, and how they manage
today; what exists already; why now, and the appetite; how success is known,
and for a watched change the bar for calling it stable and roughly how long
to watch; the risks and constraints; and the fit with the product's brief.
Small: what and why, in a line, and for a watched change its bar for
stable.>

## Requirements

<Small: what must be true once the change is done, any product requirement
it adds, changes or removes, and what users must be told, when it changes
what they use. Medium and large: the acceptance criteria, with their IDs,
including the edge and failure cases; the product's requirements the change
adds, changes or removes; any business rule or internal requirement it would
break; and what it leaves out. For a large change, an outline; the change's
document holds them in full.>

## Product and UX design

<When users see the change. Small: what they see afterwards, the states it
touches, and what users must be told, and where. Medium and large: its
flows as breadboards, with the IDs of the capabilities each serves, each
place's states, and its words; what users must be told, and where; and any
convention of the product's UX design it departs from. For a large change,
it is written in the change's document instead. Leave the section out when
users do not see the change.>

## Size

<S, M or L, and the trigger that sets it. Watched in production or not, and
its trigger. In a project with districts, the districts it touches, and the
district of any code it adds. A change that touches more than one lays out
its Requirements, Product and UX design, Approach, Design and Tests district
by district, then the seams between them; its pull requests stay in the
order they merge, each naming its districts.>

## Approach

<Medium: the architecture characteristics it touches, and any change to
the smallest set; the approach and one alternative, with why it lost; where
it sits; the structural rules it adds, changes or removes, and any it
breaks; what changes in data and trust; the dependencies it adds; the
scope; the removals; and an ADR drafted for each decision that outlives the
change. Large: a link to the change's document once it exists. Leave the
section out for a small change.>

## Design

<Medium: each interface another component calls that the change adds or
changes, as a stub with its doc comment and no body, or, when it only loses
a parameter, listed with what it loses; how the design meets each
architecture characteristic it touches, and how that is checked; what it
makes unnecessary, each with the pull request that removes it, or
"nothing"; and the pull requests, one per task, in the order they merge,
each with what it builds on and the IDs it proves, or the `debt` issue it
pays. Large: a link to the change's document once it exists. Leave the
section out for a small change.>

## Tests

<The test plan, with the `testing-a-change` skill. Small and medium: each
test with what it proves and the IDs it proves, its level, size, purpose and
suite, smoke when it is one, the components it covers when the project
selects tests by them, and the pull request that writes it; for a bug
fix, the test that reproduces the bug comes first. Also each existing test
the change removes or alters, with what is behind it. Large: a link to the
test plan in the change's document.>
