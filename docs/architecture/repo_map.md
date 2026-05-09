# Argus Lab Repository Map

---

# Root

```text
/mnt/g/ai/projects/argus-lab
```

---

# Structure

```text
.
├── README.md
│
├── docs/
│   ├── README.md
│   │
│   ├── ai-operations/
│   │   ├── prompting_strategy.md
│   │   └── resume_prompt.md
│   │
│   ├── architecture/
│   │   ├── argus_lab_system_prompt.md
│   │   ├── argus_lab_v1_blueprint.md
│   │   └── repo_map.md
│   │
│   ├── build/
│   │   └── README.md
│   │
│   ├── operations/
│   │   └── README.md
│   │
│   ├── scenarios/
│   │   └── README.md
│   │
│   ├── training/
│   │   └── README.md
│   │
│   ├── validation/
│   │   └── README.md
│   │
│   └── vision/
│       └── argus_lab_vision.md
│
├── scripts/
│   ├── faults/
│   │   └── README.md
│   │
│   ├── resets/
│   │   └── README.md
│   │
│   └── utilities/
│       └── README.md
│
├── build-logs/
│   └── 001_homelab_foundation.md
│
└── .git/
```

---

# System Relationships

## NeuroCore

```text
/mnt/g/ai/projects/neurocore
```

NeuroCore is the controlled AI platform that Argus ACLI is built on.

Argus Lab is intended to integrate with NeuroCore and Argus ACLI as the platform matures.

---

## Argus Lab Repo

```text
/mnt/g/ai/projects/argus-lab
```

This repository is the source of truth for Argus Lab planning, architecture, training design, validation design, scenario structure, reset workflows, and future lab implementation.

---

## Future VM Infrastructure

VM storage is outside the repository.

Current/future VM storage location should be documented when implementation begins.

Planned direction:

```text
G:\argus-lab\vms\
```

Historical note:

```text
G:\homelab\vms\
```

was the original planned storage path when this project was still named Homelab.

---

# Documentation Roles

## Root README

```text
README.md
```

Public front door for the Argus Lab repository.

Explains:

- what Argus Lab is
- how it started
- how it matured
- human training role
- NeuroCore / Argus ACLI validation role
- model-guided troubleshooting direction
- current status

---

## Vision

```text
docs/vision/argus_lab_vision.md
```

Long-term vision for Argus Lab.

Explains:

- why Argus Lab exists
- real troubleshooting skill
- resettable sessions
- adaptive difficulty
- model-guided mentoring
- tracked progression
- long-term certification direction

---

## Architecture

```text
docs/architecture/
```

Contains system design and structural reference documents.

Current files:

```text
argus_lab_system_prompt.md
argus_lab_v1_blueprint.md
repo_map.md
```

---

## AI Operations

```text
docs/ai-operations/
```

Contains reusable AI collaboration, prompting, and resume context for future build sessions.

---

## Scenarios

```text
docs/scenarios/
```

Future home for controlled fault scenario definitions.

This should eventually include:

- scenario format
- fault categories
- difficulty tiers
- expected symptoms
- injected faults
- recovery criteria
- learning objectives

---

## Validation

```text
docs/validation/
```

Future home for NeuroCore, Argus ACLI, and model-guidance validation strategy.

This should eventually include:

- diagnostic accuracy testing
- severity classification validation
- recommendation validation
- regression testing
- model-guided troubleshooting evaluation

---

## Training

```text
docs/training/
```

Future home for learner progression and training design.

This should eventually include:

- guidance modes
- mentor behavior
- user progression
- skill tracking
- proficiency levels
- demonstrated-ability certification direction

---

## Operations

```text
docs/operations/
```

Future home for lab operation and maintenance.

This should eventually include:

- environment setup
- known-good states
- reset workflow
- session lifecycle
- maintenance procedures

---

## Build

```text
docs/build/
```

Future home for build planning and implementation notes that are not formal build logs.

---

## Build Logs

```text
build-logs/
```

Chronological implementation history.

Existing historical file:

```text
001_homelab_foundation.md
```

This file preserves the original project identity and should not be renamed unless there is a dedicated history cleanup decision.

Future build logs should use Argus Lab naming.

---

## Scripts

```text
scripts/
```

Future home for lab automation.

Subdirectories:

```text
scripts/faults/
scripts/resets/
scripts/utilities/
```

Rules:

- fault scripts inject controlled failures
- reset scripts restore known-good states
- utility scripts support lab operation
- scripts must be documented before use
- every fault must have a reset path

---

# Rules

- Do not guess paths.
- Always reference this map before editing structure.
- Repository is the source of truth for all design and implementation planning.
- VMs must not be stored inside the repository.
- Scripts must live in the repository.
- Documentation must reflect real filesystem state.
- Update this map immediately when structure changes.
- Preserve historical context where useful, but use Argus Lab naming for all new public-facing work.
- No BayerTech naming should appear in new public-facing documentation.

---

# Current Status

The repository has been renamed conceptually from Homelab to Argus Lab.

Current active identity:

```text
Argus Lab
```

Current repo path:

```text
/mnt/g/ai/projects/argus-lab
```

Current phase:

```text
public documentation and repository organization
```

Implementation has not yet begun.

The current focus is organizing the repository so future build work, fault scenarios, validation logic, training flows, and automation do not become scattered.

---

# End of Map