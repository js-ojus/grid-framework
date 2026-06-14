# The `GRID` Framework

`GRID` is a framework for projects that commit to using coding agents in a specification-driven manner.
This is of limited use to projects that employ vibe-coding.
Accordingly, the `GRID` framework requires discipline on the part of the user to adhere to spec-driven development.

Given that discipline, `GRID` helps in:

* ensuring a certain degree of sanity in the specification, and
* ensuring a certain degree of honesty in the agreement between the specification, the code, and the tests.

`GRID` is small framework, by design.
Also — by itself — `GRID` is *not* prescriptive; and, again, intentionally so!

However, this simplicity can be deceptive.
`GRID` has consistently delivered value on projects of various sizes, architectures, and tech stacks.

## Basic Usage

Your specification can be in a single file or spread over multiple files in a given directory.
The entry point file must be named `SPEC.md`.
In case the specification is broken into multiple files, `SPEC.md` must refer to all of them.

First, save a copy of `GRID.md` in the root of your `git` directory.
Or, point your agent at this GitHub repository itself.

Then, whenever the specification changes independently of the code or the code changes independently of the specification, point your agent at `GRID.md` and ask it to perform as specified therein.
For convenience, you can include a corresponding instruction in your project's `AGENTS.md`.

Create a file `acceptable-deviations.md` in the same directory as `SPEC.md`.

- For each coding agent available:
  - Perform `GRID` analysis.
  - For each observation:
    - If an observation is acceptable:
      - Address the observation.
    - Else:
      - Add it to `acceptable-deviations.md`.

Optionally, you can run the above loop another time (or as many times as needed).
That can surface issues that get introduced in the process of addressing an observation.

## Advanced Usage

You can make `GRID` an integral part of your CI/CD pipeline.
Here are a few example possibilities.

* Alert different stakeholders for observations in different areas.
  * _E.g._ Security risks are sent to the security architect, while spec-test discrepancies are sent to the test lead.
* Alert appropriate stakeholders only upon the `GRID` analysis making one or more `High` severity observations.
  * Optionally, you could set a threshold on the number of `High` severity observations, beyond which the pipeline stops.
* You could pass an algorithmic inconsistency to the next stage, while choosing to block on a specification ambiguity.
