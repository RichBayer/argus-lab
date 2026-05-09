# Argus Lab Scenarios

---

## Purpose

This directory will contain controlled fault scenario definitions for Argus Lab.

Scenarios are the core training and validation unit of the lab.

Each scenario should represent a realistic Linux problem that can be injected, investigated, repaired, validated, and reset.

---

## Scenario Goals

Each scenario should support two goals:

1. help users practice real Linux troubleshooting
2. validate NeuroCore, Argus ACLI, and model-guided troubleshooting behavior against a known fault

---

## Future Scenario Metadata

Each scenario should eventually define:

- scenario ID
- title
- difficulty level
- affected systems
- injected fault
- expected symptoms
- relevant evidence
- intended learning objectives
- validation checks
- recovery criteria
- reset method
- guidance strategy
- model guidance behavior
- NeuroCore / Argus validation purpose

---

## Difficulty Direction

Scenarios should become more difficult as the user improves.

Early scenarios may focus on:

- obvious symptoms
- single-system issues
- simple permissions failures
- stopped services
- basic log investigation

Later scenarios may include:

- noisy logs
- misleading symptoms
- multiple contributing faults
- multi-system dependencies
- incomplete information
- deeper Linux concepts
- advanced infrastructure technologies

---

## Rule

Every scenario must have a reset path.

No fault should be created without a way to return the environment to a known-good state.
