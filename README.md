# The `GRID` Framework

`GRID` is a framework for projects that commit to using coding agents in a specification-driven manner.
This is of limited use to projects that employ vibe-coding.
Accordingly, the `GRID` framework requires discipline on the part of the user to adhere to spec-driven development.

Given that discipline, `GRID` helps in:

* ensuring a certain degree of sanity in the specification, and
* ensuring a certain degree of honesty in the agreement between the specification, the code, and the tests.

Your specification can be in a single file or spread over multiple files in a given directory.

## How To Use The `GRID` Framework?

First, save a copy of `GRID.md` in the root of your `git` directory.

Then, whenever the specification changes independently of the code or the code changes independently of the specification, point your agent at `GRID.md` and ask it to perform as specified therein.

Create a file `acceptable_deviations.md` in the same directory as `SPEC.md`.

- For each coding agent available:
  - Perform `GRID` analysis.
  - For each observation:
    - If an observation is acceptable:
      - Address the observation.
    - Else:
      - Add it to `acceptable_deviations.md`.

Optionally, you can run the above loop another time (or as many times as needed).
That can surface issues that get introduced in the process of addressing an observation.
