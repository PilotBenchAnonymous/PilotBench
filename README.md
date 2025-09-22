# PILOT-Bench Supplementary (Tasks & Tools)

This repository contains the supplementary materials submitted with the paper:
- Tasks (task specifications and reference workflows): a set of JSON files under the `tasks/` directory.
- Tools (tool registry / probabilistic tool behavior): the `tool_registry.json` at the repository root.

The sections below explain how these files map to the paper and provide a unified naming scheme for easier review and reproduction.

## Relation to the Paper
- Tool Registry (Tools) → Paper “Benchmark Setup” → “Tool Registry”, consistent with “Benchmark Construction > Tool Library Generation”. Error models and dependencies are detailed in the paper and appendices.
- Tasks and Reference Workflows (Tasks + Workflows) → Paper “Benchmark Setup > Benchmark Data Organization” → “Task Specifications” and “Reference Workflows”. The four prompt variants correspond to “Workflow Prompt Generation” and “MDP-BASED OPTIMAL WORKFLOW GENERATION”.

## Files and Contents
- `tool_registry.json`
  - Tool registry of APIs, including parameter templates, return schemas, and probabilistic error models (INVALID_INPUT, OPERATION_FAILED, TIMEOUT, CALCULATION_ERROR, OVERFLOW).
  - Corresponds to the “Tool Registry” implementation in the paper.

- `tasks/*.json`
  - Task sets, organized by difficulty and whether reference workflows are included:
    - Files with the suffix `_with_workflows.json`: extend task specifications with four prompt variants (Baseline / Chain-of-Thought / Optimal Workflow / Flawed Workflow).
    - Files without that suffix: contain only Task Specifications.
    - File names that include `biased`: indicate a biased sampling/configuration variant for supplemental analysis (does not affect the main definitions in the paper).

## Quick Filename Mapping
- Tools → `tool_registry.json` (Paper “Tool Registry”).
- Tasks (without workflows) → `tasks/task_specs_v3_{difficulty}.json` (Paper “Task Specifications”).
- Tasks (with four reference workflows) → `tasks/task_specs_v3_{difficulty}_with_workflows.json` (Paper “Reference Workflows”, “Workflow Prompt Generation”, “MDP-BASED OPTIMAL WORKFLOW GENERATION”).
- `biased` variants → supplemental analysis dataset versions (for robustness/sampling comparisons).



