# Reset Scripts

---

## Purpose

This directory will contain scripts that restore Argus Lab systems to known-good states after fault injection and troubleshooting sessions.

Reset scripts are required for repeatable practice.

---

## Rules

Every reset script must:

- be tied to a known fault or scenario
- restore the affected system to a documented known-good state
- be safe to run repeatedly
- avoid destructive behavior outside the intended scenario
- include validation where possible

---

## Scenario Lifecycle

Reset scripts support this loop:

    known-good state
    -> injected fault
    -> investigation
    -> repair attempt
    -> validation
    -> reset
    -> next scenario

---

## Critical Rule

Reset logic is part of scenario design.

It is not optional.
