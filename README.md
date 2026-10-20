# Kraken Knowledge Architecture

## Overview

This project proposes a modular knowledge and instruction architecture for Kraken, an AI assistant supporting Doctoralia professionals. It is based on the supplied Doctor–Kraken conversation and demonstrates how observed product knowledge can be structured for reuse across assistant instructions and human-readable support articles.

The deliverable is a **no-code architecture and content prototype**, not a deployed assistant, retrieval service, or automated generation pipeline.

## Architecture

```
                    TAXONOMY
             (classification framework)
                         │
                         ▼
INVENTORY ───────────► MODULES
(source facts and        │
 evidence)               ▼
                     OUTPUTS
               ┌─────────┴─────────┐
               ▼                   ▼
        Kraken instructions    Support articles
```

The taxonomy is the overarching classification framework. The inventory records source-grounded facts and their identifiers. Both inform the modules, which separate product rules, workflows, and interface terminology. Modules are then reused to produce two distinct outputs: task-specific instructions for Kraken and articles for human readers.

### 1. Taxonomy — `taxonomy/kraken-basic-taxonomy.yml`

Defines a common vocabulary for features, tasks, roles, consultation types, access points, subscription plans, and profile types. Its terms help organize and discover knowledge. The taxonomy may be broader than the facts covered by the current source material; a taxonomy entry does not imply a fully documented procedure.

### 2. Product fact inventory — `inventory/kraken-product-facts.md`

Captures facts from the supplied conversation with stable identifiers, grouped into product rules (`PR`), procedures and workflows (`PW`), UI elements (`UI`), outcomes and side effects (`OS`), and escalation triggers (`ET`). It provides traceability from modular knowledge back to the supplied source and makes gaps visible.

### 3. Reusable knowledge modules — `modules/`

- `rules.yml`: constraints, permissions, prerequisites, and consequences.
- *`procedures.yml`: actions, workflows, and troubleshooting steps.
- `ui.yml`: interface labels, controls, and navigation terminology, including localized content.

Each module entry has a stable ID, taxonomy tags, and `source_facts` references. Separating these concerns reduces duplication and allows the same product knowledge to support different tasks and audiences.

### 4. Kraken instructions — `instructions/`

The global instruction file defines shared assistant behavior, such as routing, uncertainty handling, permissions, and escalation. Task-specific Markdown files define the task and its module dependencies rather than repeating detailed product facts. Their front matter distinguishes common dependencies, task branches, and conditional troubleshooting knowledge. The intent is to retrieve only the relevant knowledge for a given request.

### 5. Human-readable articles — `articles/`

Two articles demonstrate different presentations of the same underlying knowledge:

- An external guide for professionals managing consultation locations.
- An internal troubleshooting guide for support specialists diagnosing issues and deciding when to escalate.

Article front matter identifies audience, language, and source-module dependencies at section level. These references could help a future update process identify which articles and sections are affected when a module changes. Article generation and publication are **not automated in this prototype**.

## Why this approach

**Maintainability.** Product facts and modules are maintained in distinct, reusable locations rather than duplicated across instructions and articles.

**Scalability.** New tasks, product areas, roles, and localized outputs can reuse existing modules. The taxonomy can expand without requiring unsupported procedures to be invented.

**Automation friendliness.** Structured, explicit dependencies, and metadata provide inputs for future retrieval, validation, regeneration, and publication automation workflows.

**Traceability and audience separation.** Module entries point to inventory facts, while output dependencies point back to modules. Kraken instructions focus on orchestration; external and internal articles present information differently according to their readers.

## Manual validation and testing scope

Consistency checks were performed during drafting across the inventory, taxonomy, modules, instructions, and articles. A final coverage review of the three knowledge modules found:

- **77 of 78** inventoried product facts referenced by at least one module. The unreferenced fact (`PR-13`) concerns changing calendar color in the mobile app, outside the selected workflows.
- **27 of 36** leaf taxonomy terms referenced by at least one module. The other nine represent broader capabilities or categories without corresponding captured module content.
- No references to nonexistent inventory fact IDs or taxonomy terms in the reviewed modules.

These are manual design-level coverage and reference checks, not executed tests of Kraken.

## Potential next steps

1. **Refine the inventory structure.** Split the inventory into more granular, typed product-fact categories or files as coverage grows, while retaining stable fact IDs and provenance.
2. **Introduce a RAG pipeline.** Index appropriate module content in a vector database and use taxonomy, metadata, and dependency rules to retrieve relevant knowledge. Vector similarity should complement, not replace, explicit rule and dependency selection.
3. **Build Python executors.** Implement separate workflows for updating task instructions and regenerating affected article sections from changed modules, with dependency resolution, structured prompts, and human approval before publication.
4. **Add automated Python testing.** Validate schemas and IDs, detect broken references, verify dependency coverage, and run scenario-based routing and generated-answer evaluations against expected behavior.
5. **Integrate CI/CD.** Trigger checks on knowledge changes, report impacted outputs, generate reviewable updates, and publish approved versions with traceable change history.

Localization can follow the same model: localized outputs retain their logical identity and source dependencies while using locale-appropriate UI terminology and editorial review.

## Scope and limitations

This prototype demonstrates information architecture, modular content, and output traceability using the supplied conversation as its source. It does not implement a vector database, Python executors, automated generation, automated testing, or CI/CD. Product behavior is represented as stated in the supplied source rather than independently tested in a live Doctoralia environment.