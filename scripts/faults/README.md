# Fault Injection Scripts

---

## Purpose

This directory will contain scripts that inject controlled faults into Argus Lab systems.

Fault scripts create realistic Linux problems for training and validation.

---

## Rules

Every fault script must:

- be intentional
- be documented
- be reversible
- have a matching reset path
- define affected systems
- define expected symptoms
- support validation
- avoid permanent damage

---

## Naming Direction

Future script naming should be consistent and scenario-linked.

Example direction:

    scenario_001_inject.sh
    scenario_002_inject.sh

Exact naming may change once the scenario format is finalized.

---

## Critical Rule

No fault script should be created without a reset strategy.
