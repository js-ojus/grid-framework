# `GRID`

When the user asks for a `GRID` analysis, perform the following.

* Read the changes to the specification, starting with `SPEC.md`.
  In case `SPEC.md` refers to other files, read their changes too.
  * These could be the uncommitted changes.
  * These could be since the most recent previous commit.
  * These could be since a user-specified commit/tag.

* Read the changes to the code.
  * These could be the uncommitted changes.
  * These could be since the most recent previous commit.
  * These could be since a user-specified commit/tag.

* Read the changes to the tests.
  * These could be the uncommitted changes.
  * These could be since the most recent previous commit.
  * These could be since a user-specified commit/tag.

* Read the file `acceptable-deviations.md`, if one exists.

Use all of the above as the most immediate context for the following.

* Perform the `GRID` analysis as detailed in the next section and give your observations.

* Do not give out an observation in case it is already recorded in `acceptable-deviations.md`.

* Assign a "**Severity**" rating to each observation: `High`, `Medium`, or `Low`, based on the degree of adverse impact that the underlying cause could have.
  * Reason from at least one additional angle/perspective before flagging an observation with a `High` severity.

* Consistently provide line number references (multiple ranges, in multiple files, where necessary) for each observation.

## The `GRID` Analysis

**GRID** stands for **G**aps, **R**isks, **I**nconsistencies, and **D**iscrepancies.

**GAPS**

Analyse the specification for:

* areas of under-specification that could impair implementation (labelled "G-US-_n_"), and
* ambiguities that could lead to spec-compliant, yet divergent implementations (labelled "G-AM-_n_").

**RISKS**

Analyse the specification, the code, and the tests for:

* architecture risks (labelled "R-AR-_n_"),
* design risks (labelled "R-D-_n_"),
* algorithmic risks (labelled "R-AL-_n_"), and
* security risks (labelled "R-S-_n_").

**INCONSISTENCIES**

Analyse the specification for:

* internal inconsistencies (labelled "I-I-_n_"),
* major deviations with generally accepted industry best practices (labelled "I-BP-_n_"), and
* broken cross-references and orphans (labelled "I-BO-_n_").

**DISCREPANCIES**

Analyse the specification, the code, and the tests for:

* spec–code discrepancies (labelled "D-SC-_n_"),
* code–test discrepancies (labelled "D-CT-_n_"), and
* spec–test discrepancies (labelled "D-ST-_n_").

## Output

Write the observations out to a file into the directory `docs/grid`.
The naming of these files should follow the convention: `YYYYMMDD-nnnnn-<agent>-<title>.md`.

* Here, `<agent>` is a canonical snake-case name of yourself (the agent that has made these observations).
* `<title>` is a meaningful short name for this set of observations; this is in snake-case, as well.
