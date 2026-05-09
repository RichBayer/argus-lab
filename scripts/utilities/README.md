# Utility Scripts

---

## Purpose

This directory will contain helper scripts used to support Argus Lab operation.

Utility scripts are not fault injections and are not scenario resets.

---

## Possible Uses

Future utilities may support:

- baseline checks
- environment validation
- service status checks
- network checks
- scenario listing
- repo maintenance
- lab health checks

---

## Rules

Utility scripts must:

- be documented
- avoid hidden side effects
- avoid changing system state unless clearly intended
- support repeatable lab operation
- remain separate from fault and reset scripts

---

## Critical Rule

If a utility changes system state, document exactly what it changes and why.
