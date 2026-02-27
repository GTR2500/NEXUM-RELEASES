# NEXUM

### Deterministic Technical Governance for Manufacturing

[![Release](https://img.shields.io/badge/release-stable-blue.svg)](https://github.com/GTR2500/NEXUM-RELEASES/releases)

This public repository exposes **only the current stable release** of Nexum.

Previous releases are **not** retained publicly.  
They are archived internally for auditability, traceability, and compliance.

This is a governance decision, not a limitation.

---

## What Nexum is

Nexum is a modular desktop suite designed to orchestrate

- technical codification
- bills of materials
- hierarchical structures
- ERP-ready exports
- inter-module governance

It is not a single-purpose tool.  
It is a control layer over manufacturing technical processes.

---

## Architecture

| Layer | Stack |
|-------|-------|
| **Desktop runtime** | Electron 33 |
| **UI** | React 18, TypeScript, Vite |
| **Technical parsing** | XLS/XLSX via xlsx |
| **Internal communication** | IPC isolated via contextBridge |

No mandatory backend.  
No required cloud dependency.

---

## Modular pipeline

The sequence is enforced

**Codexa → Axion → Structor → NexFlow**

Operating principles

- a module does not alter certified outputs produced upstream
- registries are monotonic and never reused
- collision guards are mandatory
- preview is a gate before execution
- exports are standardized
- audit is kept separate from target outputs

> **Determinism > Convenience**

---

## Codexa

Responsibilities

- parts codification (GR39)
- assembly codification (GR90<COMMESSA8>-FNNN)
- multi-extension rename clustered by BaseKey
- collision guards within and across groups
- Concept-ready exports

Contractual mapping CSV header (immutable order)

```
OLD_CODE;NEW_CODE;OLD_FILE;NEW_FILE;STATO
```

---

## Axion

Responsibilities

- hierarchical BOM construction
- parent-child validation
- export `AXION_DISTINTA_BASE_<COMMESSA8>.xls`
- audit JSON and technical diagnostic CSV

Loader priority

1. Manifest  
2. Explicit legacy fallback

---

## Governance

- `MODULE_REGISTRY` as the source of truth
- module state separated from licensing
- enabled/licensed gating at runtime

---

## Release policy

- only one stable release is published at a time
- each new stable release replaces the previous one
- versioning follows SemVer
- published artifacts are official builds produced by a controlled pipeline

This repository is not a historical archive.  
It is a stable release channel.

---

## Target users

Nexum is designed for

- structured manufacturing SMEs
- multi-job environments
- ERP contexts requiring codification consistency

It is not intended for hobby usage.

---

## Integrity

Each stable build

- derives from a segregated workspace
- is verifiable via hash
- respects declared inter-module contracts

---

## Licensing and distribution

For activation, licensing, and official distribution, contact:

**Software House** — Manuel Zago  
visualart.lab.mi@gmail.com
