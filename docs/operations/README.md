# Argus Lab Operations

---

## Purpose

This directory will contain operational documentation for running and maintaining Argus Lab.

Operations documentation should explain how the lab is built, reset, maintained, and validated.

---

## Future Topics

This directory should eventually include:

- environment setup
- VM lifecycle
- known-good states
- reset workflows
- session lifecycle
- network configuration
- service baselines
- maintenance procedures
- backup and restore strategy
- validation before and after scenarios

---

## Known-Good States

Argus Lab depends on known-good states.

A known-good state is the baseline condition a system should return to after a scenario is complete.

Every fault scenario should be designed around:

    known-good state
    -> injected fault
    -> investigation
    -> repair attempt
    -> validation
    -> reset
    -> known-good state

---

## Rule

Operational procedures must reflect real system behavior.

Do not document intended behavior as if it has already been validated.
