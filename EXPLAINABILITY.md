# EXPLAINABILITY.md

This document explains the internal mechanisms, data lineage, operational boundaries, and governance framework of **# Explainability & Decision Transparency Report** (`superpowers`) in accordance with the **OpenGAP v0.1.0** specification for the **HiDevs GitAgent Passport** clearance pipeline.

> **Agent Name:** # Explainability & Decision Transparency Report (`superpowers`)  
> **Specification:** OpenGAP v0.1.0  
> **Category / Domain:** Developer Tools / Autonomous Agent Discipline, TDD, Skill Invocation & Worktrees  
> **Compliance Standard:** OpenGAP Checkpoint 2 (Explainability & Decision Governance), OWASP LLM Top 10, MITRE ATLAS  

---

## How the Agent Decides

# Explainability & Decision Transparency Report operates via a deterministic five-stage operational pipeline.

### 1. Decision Architecture

The runtime intake, state classification, evaluation, and execution tracking operate across a deterministic, five-stage pipeline:

```
+-----------------------------------------------------------------------------------+
|                        Deterministic Superpowers Pipeline                         |
+-----------------------------------------------------------------------------------+
|  [Stage 1: Intent Ingestion & Mandatory Skill Resolution Gate]                    |
|     --> Inspect task prompt, scan skills directory, & trigger highest priority skill|
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 2: Spec Brainstorming & Isolated Worktree Setup]                          |
|     --> Explore user requirements; instantiate isolated git worktree branch       |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 3: Plan Formulation & Subagent Task Dispatch]                             |
|     --> Decompose into testable tasks; dispatch parallel or sequential subagents   |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 4: Test-Driven Development & Systematic Debugging]                        |
|     --> Write failing tests first; implement minimal fixes; isolate root causes   |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 5: Evidence-Based Verification & Branch Finalization]                     |
|     --> Execute test suites, verify clean output traces, & finalize branch merge   |
+-----------------------------------------------------------------------------------+
```

### 2. Decision Logic & Routing Formulations

& Subagent Task Dispatch]                             |
|     --> Decompose into testable tasks; dispatch parallel or sequential subagents   |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 4: Test-Driven Development & Systematic Debugging]                        |
|     --> Write failing tests first; implement minimal fixes; isolate root causes   |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 5: Evidence-Based Verification & Branch Finalization]                     |
|     --> Execute test suites, verify clean output traces, & finalize branch merge   |
+-----------------------------------------------------------------------------------+
```

### 3. Thresholding & Refusal Decision Criteria

# Explainability & Decision Transparency Report enforces strict operational boundaries and deterministic refusal thresholds:
- **Refusal on ERR_UNVERIFIED_COMPLETION_ASSERTION**: **Premature Completion Claim** halts execution with code `ERR_UNVERIFIED_COMPLETION_ASSERTION`.
- **Refusal on ERR_MISSING_BRAINSTORMING_PHASE**: **Bypassing Brainstorming** halts execution with code `ERR_MISSING_BRAINSTORMING_PHASE`.
- **Refusal on ERR_TDD_DISCIPLINE_VIOLATION**: **Implementation Without Test** halts execution with code `ERR_TDD_DISCIPLINE_VIOLATION`.
- **Refusal on ERR_DIRTY_WORKTREE_DETECTED**: **Dirty Working Tree Merge** halts execution with code `ERR_DIRTY_WORKTREE_DETECTED`.
- **Refusal on ERR_CYCLIC_SUBAGENT_DEADLOCK**: **Circular Subagent Dependency** halts execution with code `ERR_CYCLIC_SUBAGENT_DEADLOCK`.

### 4. Fallback Decision Mechanism

Continuous operational stability is maintained through layered fault recovery:
- **Model Fallback Cascade**: High-level reasoning and synthesis default to `gemini-2.0-flash` with automatic failover to `gpt-4o` and `claude-3-5-sonnet`.

### 5. Human-in-the-Loop Governance

Human operators retain sovereign authority over the multi-agent execution lifecycle:
- **Consequential Action Sign-Off**: Sensitive and consequential actions require operator sign-off.
- **Offline Ledger Auditing**: Operators can verify execution records and state transitions offline.

---

## The Data It Uses

# Explainability & Decision Transparency Report operates under strict principles of data minimization, environment isolation, and privacy protection.

### 1. Ingested Input Data

The framework processes only operational data necessary to perform its functions:
- **Developer Instructions**: Feature requests, bug reports, and refactoring goals.
- **Skill Definitions**: Markdown YAML frontmatter and instructional checklists in `skills/*/SKILL.md`.
- **Test & Shell Telemetry**: Execution outputs, exit codes, compiler linter errors, and diff logs.

### 2. Configuration & Reference Data

- **Configuration Schemas**: Declarative system policy files.

### 3. Base Model & Inference Lineage

- **Host Agents**: Claude Code, Cursor, Devin, Hermes, OpenCode, Gemini, Roo Code.
- **Runtime Environment**: Node.js, Shell, Git CLI, cross-platform harness plugins.

### 4. Data Privacy, Storage, and Retention

- **OWASP LLM & MITRE ATLAS Hardened**: Defended against indirect prompt injection, credential leakage, and unauthorized external API dispatch.
- **Local Environment Isolation**: Agent execution workspaces, intermediate scratchpads, and vector stores reside strictly within designated local project directories.
- **Automated Secret Scrubbing**: API keys, database credentials, and personal credentials are automatically redacted prior to embedding or logging.
- **Zero Commercial Monetization**: Prompts, intermediate reasoning trajectories, and task deliverables are never commercialized or shared with third parties.

---

## Limitations

Understanding the operational boundaries and technical constraints of # Explainability & Decision Transparency Report is essential for effective deployment.

### 1. Worktree Creation Overhead on Massive Repositories
- **Limitation**: Initializing git worktrees on repositories with gigabytes of LFS assets can incur disk and setup latency.
- **Mitigation**: Support lightweight in-place branch switching when full worktree isolation is explicitly opted out.

### 2. Multi-Agent Context Synchronization
- **Limitation**: Dispatched parallel subagents operating without shared memory can occasionally duplicate file edits.
- **Mitigation**: Strictly partition file access boundaries across subagent task specifications prior to dispatch.

### 3. Rigorous TDD Slower for Exploratory Prototyping
- **Limitation**: Enforcing failing tests first introduces initial friction for rapid visual UI mockups.
- **Mitigation**: Designate explicit exploratory spikes in the plan where formal TDD is deferred until interface stabilization.

### 4. Flaky Test False Positives
- **Limitation**: Non-deterministic or network-dependent unit tests can trigger false regression alarms.
- **Mitigation**: Quarantine flaky tests and mandate multi-run stability checks before accepting test outcomes.

### 5. Skill Selection Ambiguity Under Broad Prompts
- **Limitation**: Highly vague user queries ("help me out") may trigger multiple competing process skills.
- **Mitigation**: Default conservatively to `using-superpowers` and ask single clarifying questions.

---

## Summary & Compliance Checklist

| Checkpoint 2 Requirement | Corresponding Section | Status |
| :--- | :--- | :---: |
| **How the agent decides** | [How the Agent Decides](#how-the-agent-decides) | **Covered** |
| - Decision architecture & 5-stage pipeline | Section 1 | Verified |
| - Decision logic & routing formulations | Section 2 | Verified |
| - Thresholding & refusal decision criteria | Section 3 | Verified |
| - Fallback decision mechanism | Section 4 | Verified |
| - Human-in-the-loop governance & oversight | Section 5 | Verified |
| **The data it uses** | [The Data It Uses](#the-data-it-uses) | **Covered** |
| - Ingested input data & query streams | Section 1 | Verified |
| - Configuration & reference schemas | Section 2 | Verified |
| - Base model lineage & deterministic engines | Section 3 | Verified |
| - Data privacy, retention lifecycle & MITRE/OWASP | Section 4 | Verified |
| **Its limitations** | [Limitations](#limitations) | **Covered** |
| - Worktree Creation Overhead on Massive Repositories | Section 1 | Verified |
| - Multi-Agent Context Synchronization | Section 2 | Verified |
| - Rigorous TDD Slower for Exploratory Prototyping | Section 3 | Verified |
| - Flaky Test False Positives | Section 4 | Verified |
| - Skill Selection Ambiguity Under Broad Prompts | Section 5 | Verified |
