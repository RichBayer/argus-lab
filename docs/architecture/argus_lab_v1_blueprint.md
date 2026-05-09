# Argus Lab V1 Blueprint – Training and Validation Environment

---

# Purpose

This document defines the initial blueprint for Argus Lab.

Argus Lab is a planned real Linux troubleshooting, training, and validation environment.

It is designed to support two connected goals:

1. train people to troubleshoot real Linux systems through controlled failure scenarios
2. validate NeuroCore, Argus ACLI, and model-guided troubleshooting against realistic Linux problems

Argus Lab began as a personal practice environment for learning Linux troubleshooting.

It has matured into a future training and validation system.

---

# Design Philosophy

Argus Lab is not a collection of random VMs.

It is a structured environment designed to feel like real infrastructure.

The lab should be:

- small enough to manage
- complex enough to teach real troubleshooting
- built with defined system roles
- built with interdependent services
- designed for controlled failure and recovery
- resettable after troubleshooting sessions
- portable across hardware environments
- useful for both human training and diagnostic validation

The goal is not to memorize commands.

The goal is to develop operational judgment.

---

# Core Design Principle

> Real skill comes from solving real problems.

Argus Lab should give users real systems, real symptoms, real uncertainty, and a safe way to practice.

The environment should be built so users can:

- encounter a realistic problem
- investigate the system
- form a hypothesis
- test that hypothesis
- repair the issue
- verify recovery
- reset the environment
- try another scenario

---

# Lab Identity

## Current Project Identity

```text
Argus Lab
```

## Environment Type

```text
Real Linux troubleshooting, training, and validation environment
```

## Current Repo Path

```text
/mnt/g/ai/projects/argus-lab
```

## Planned VM Storage Direction

```text
G:\argus-lab\vms\
```

## Historical Note

This project originally began under the Homelab name as a personal Linux practice and portfolio environment.

Older build logs may preserve that history.

New public-facing documentation should use Argus Lab naming.

BayerTech naming should not be used in new public-facing docs.

---

# Relationship to NeuroCore, Argus ACLI, and the Model

Argus Lab is intended to integrate with NeuroCore and Argus ACLI as the platform matures.

Each layer has a different role.

```text
NeuroCore
  controls runtime, tool access, execution path, memory, and system interaction

Argus ACLI
  collects, structures, and interprets real Linux system data

AI model
  uses grounded Argus data to guide the learner progressively
```

Argus Lab should eventually test the full interaction between these layers.

The lab should validate:

- whether NeuroCore safely interacts with real Linux systems
- whether Argus ACLI identifies symptoms correctly
- whether severity classifications are accurate
- whether recommendations are useful
- whether raw evidence supports the findings
- whether the model can guide the user without simply giving away the answer
- whether diagnostic behavior remains consistent across repeated scenarios

---

# V1 Environment Goals

The initial Argus Lab environment should focus on core Linux system administration and troubleshooting.

V1 should be designed around:

- simple system roles
- clear network design
- realistic service dependencies
- controlled fault injection
- resettable scenarios
- repeatable validation
- beginner-to-intermediate Linux troubleshooting
- future expansion into more advanced tracks

V1 does not need to be large.

It needs to be clean, understandable, portable, and useful.

---

# Planned VM Architecture

The initial environment may include the following systems.

## Nodes

```text
client01
  admin workstation

web01
  web/application server

files01
  file and backup server

mon01
  monitoring system

infra01
  DNS and infrastructure services

legacy01
  optional degraded system for troubleshooting practice
```

The exact design may evolve, but each VM must have a clear role.

---

# VM Role Definitions

## client01

Purpose:

- administrator workstation
- user access point
- troubleshooting entry point

Possible functions:

- SSH client
- basic admin tools
- documentation access
- scenario interaction point

---

## web01

Purpose:

- web/application service host

Possible functions:

- Apache or Nginx
- internal web content
- service availability scenarios
- permissions and configuration troubleshooting

---

## files01

Purpose:

- file storage and backup target

Possible functions:

- shared directories
- backup destination
- permissions scenarios
- ownership and ACL troubleshooting

---

## mon01

Purpose:

- monitoring and health-check system

Possible functions:

- scheduled checks
- log collection
- simple alerting scripts
- visibility into system health

---

## infra01

Purpose:

- infrastructure services

Possible functions:

- DNS
- internal name resolution
- future DHCP or supporting services
- infrastructure dependency scenarios

---

## legacy01

Purpose:

- optional degraded or intentionally messy system

Possible functions:

- older configuration patterns
- inconsistent service state
- accumulated technical debt
- advanced troubleshooting practice

---

# Network Design

## Internal Network

Initial planned network:

```text
192.168.50.0/24
```

## Static IP Assignments

```text
client01  → 192.168.50.10
web01     → 192.168.50.20
files01   → 192.168.50.30
mon01     → 192.168.50.40
infra01   → 192.168.50.50
legacy01  → 192.168.50.60
```

## Network Rules

- Use fixed internal addressing.
- Keep hostnames stable.
- Avoid hypervisor-specific networking tricks where possible.
- Document all network assumptions before implementation.
- Ensure the design can migrate to future server hardware.

---

# Naming Rules

- Hostnames must remain consistent.
- VM names must match documentation.
- Scripts must reference documented names.
- Scenario definitions must reference documented names.
- Avoid personal or organization-specific naming in public-facing docs.
- Use Argus Lab naming for new work.

---

# Storage Design

## Repository Storage

The repository stores:

- documentation
- scenario definitions
- architecture plans
- validation plans
- scripts
- build logs

The repository must not store VM images.

## VM Storage

VM storage should live outside the repository.

Planned future path:

```text
G:\argus-lab\vms\
```

Suggested structure:

```text
vms/
├── client01/
├── web01/
├── files01/
├── mon01/
├── infra01/
└── legacy01/
```

## Storage Rules

- Each VM should be stored in its own directory.
- VM files must not be committed to Git.
- Thin provisioning is preferred where appropriate.
- No host-specific dependencies should be embedded inside VMs.
- Known-good states should be documented.
- Reset strategy must be considered before scenario automation begins.

---

# User and Group Model

The original lab concept included realistic users, groups, and department-style permissions.

That model remains useful because permissions and ownership issues are common real-world troubleshooting areas.

## Example Users

```text
patrice
abigail
frank
pete
karen
jerry
barbara
carmen
greg
johnny
```

## Example Service Accounts

```text
backupsvc
websvc
```

## Example Groups

```text
engineering
web
ops
management
shared
backup
```

These names are placeholders for realistic training scenarios.

They may be revised as the lab matures.

---

# Filesystem Design

## Example Root Path

```text
/srv/company/
```

## Example Structure

```text
/srv/company/
├── engineering/
├── web/
├── ops/
├── management/
├── shared/
└── backups/
```

## Permissions Model

Possible baseline:

- department directories use restricted group access
- shared directories allow cross-team collaboration
- backup directories are restricted
- setgid supports group inheritance
- ACLs support cross-team access scenarios

## Training Value

This filesystem model can support scenarios involving:

- incorrect ownership
- missing group membership
- broken ACLs
- bad directory permissions
- service account access problems
- backup permission failures
- shared directory misconfiguration

---

# Service Architecture

## web01

Possible services:

- Apache or Nginx
- internal web content
- application-style directory permissions
- web service availability checks

## files01

Possible services:

- file storage
- backup destination
- shared directory access
- permissions and ownership scenarios

## mon01

Possible services:

- cron jobs
- health monitoring scripts
- simple alerting
- service status checks

## infra01

Possible services:

- DNS
- infrastructure dependency services
- name-resolution troubleshooting

## legacy01

Possible services:

- intentionally degraded or inconsistent service state
- old configuration patterns
- advanced troubleshooting scenarios

---

# Dependency Model

Initial dependency direction:

```text
infra01
↓
web01 / files01
↓
mon01
↓
client01
```

This means:

- infrastructure services affect other nodes
- web and file systems depend on infrastructure
- monitoring observes system behavior
- client01 is the main troubleshooting entry point

Dependencies should be simple at first and become more complex over time.

---

# Controlled Fault Injection Strategy

Argus Lab uses controlled fault injection instead of random breakage.

Every fault should be:

- intentional
- documented
- reversible
- testable
- tied to a learning objective
- tied to validation criteria

Faults should not permanently damage the environment.

Fault injection exists to create safe, repeatable troubleshooting practice.

---

# Fault Difficulty Tiers

## Tier 1 – Basic Single-System Issues

Examples:

- service stopped
- incorrect file permissions
- missing group membership
- simple DNS failure
- disk usage warning
- obvious log error

Goal:

teach core troubleshooting habits.

---

## Tier 2 – Intermediate Issues

Examples:

- service misconfiguration
- ACL conflict
- failed scheduled job
- incorrect ownership across service paths
- multiple symptoms from one root cause

Goal:

teach investigation and evidence comparison.

---

## Tier 3 – Multi-System Issues

Examples:

- DNS issue causing web access failure
- file server permission problem affecting service behavior
- monitoring alert caused by upstream dependency
- network reachability issue across nodes

Goal:

teach dependency reasoning.

---

## Tier 4 – Incident-Style Scenarios

Examples:

- multiple contributing faults
- noisy logs
- misleading symptoms
- degraded legacy system behavior
- partial recovery
- time-sensitive investigation

Goal:

teach operational judgment under realistic uncertainty.

---

# Adaptive Difficulty

Argus Lab should become harder as the user improves.

Early scenarios should be direct and focused.

Later scenarios can introduce:

- misleading symptoms
- noisy logs
- partial failures
- multi-system dependencies
- incomplete information
- faults that require deeper Linux knowledge
- increasingly advanced technologies

The lab should adapt from basic troubleshooting into progressively harder operational problem-solving.

As the user gets stronger, the failures should get smarter too.

---

# Resettable Scenario Design

Every scenario must have a reset path.

A scenario lifecycle should look like this:

```text
known-good state
→ injected fault
→ investigation
→ repair attempt
→ validation
→ reset
→ next scenario
```

Each scenario should define:

- known-good state
- injected fault
- expected symptoms
- validation method
- recovery criteria
- reset method

Reset logic is part of the scenario.

It is not optional.

---

# Scenario Metadata Model

Every scenario should eventually define:

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

# Training Capabilities

Argus Lab is designed to support real Linux troubleshooting skill across core domains.

## System Management

- process management
- service management
- system monitoring
- uptime and load analysis

## Security and Permissions

- file permissions
- ownership
- groups
- ACLs
- service account access
- basic hardening concepts

## Scripting and Automation

- Bash scripting fundamentals
- cron jobs
- task automation
- monitoring scripts
- fault and reset scripts

## Troubleshooting

- service failures
- permission issues
- network issues
- log analysis
- dependency failures
- multi-system scenarios

## Networking

- IP configuration
- DNS resolution
- connectivity troubleshooting
- firewall misconfiguration
- service reachability

## Storage

- disk usage
- file systems
- mounts
- backup and recovery
- permissions on storage paths

---

# Validation Capabilities

Argus Lab should eventually validate the diagnostic system as well as the learner.

It should support testing:

- NeuroCore controlled interaction with real systems
- system tool data collection
- Argus ACLI diagnostic interpretation
- severity classification
- recommendation quality
- raw evidence preservation
- model-guided troubleshooting behavior
- regression behavior across repeated scenarios

Validation should be tied to known injected faults.

A known fault gives the system a known expected answer.

That makes diagnostic behavior measurable.

---

# Mentor-Mode Behavior

Production Argus should help users understand what is happening quickly.

Argus Lab mentor mode has a different job.

It should guide without immediately giving away the answer.

Instead of saying only:

> The web service is down because Nginx is stopped.

mentor mode may ask:

> What does the service state show?
> Which log would confirm why it failed?
> What would you check before restarting it?

Mentor mode should help the learner build reasoning habits.

The model should use grounded Argus diagnostic data to provide progressive guidance.

---

# Portability and Migration Strategy

## Core Rules

- no host-specific dependencies
- no hypervisor-specific reliance where possible
- all configs reproducible
- VM storage outside repo
- documentation inside repo
- scripts inside repo

## Externalized State

All system design should be stored in the repository:

- users and groups
- directory structure
- permissions model
- service roles
- scenario definitions
- fault scripts
- reset scripts
- validation checks

## Migration Workflow

Future migration should follow a documented process such as:

1. copy VM directories
2. import into new hypervisor
3. validate network configuration
4. boot systems
5. verify services
6. run baseline validation checks

## Success Condition

Migration should not require rebuilding the lab from scratch.

---

# Current Status

Current phase:

```text
public documentation and repository organization
```

Implementation status:

```text
not yet built
```

Current focus:

- align public-facing documentation
- organize repository structure
- preserve original project history
- define future training and validation direction
- prepare for clean implementation later

---

# What V1 Should Not Do Yet

V1 should not attempt to implement everything at once.

Avoid:

- large-scale hosted platform work
- certification systems
- user account tracking
- advanced scoring engines
- uncontrolled automation
- complex multi-tenant infrastructure
- advanced scenario orchestration before basic scenarios work

Those ideas belong to later phases.

V1 should first prove the foundation:

```text
real systems
+
controlled faults
+
resettable sessions
+
useful training
+
measurable validation
```

---

# Guiding Principle

> Train like systems break. Validate like results matter. Reset so users can practice again.

---

# End of Document
