# UCP Core (ucp_nan) Style Guide

<!--*
freshness: { owner: 'chadliu' reviewed: '2026-03-21' }
*-->

This guide defines the standards for the core UCP specification repository, focusing on protocol architecture, documentation integrity, and brand neutrality.

## Core Principles

### 1. Brand Neutrality (CRITICAL)
As the source of truth for the protocol, this repository must be strictly agnostic.
*   **DO NOT** use brand names (e.g., Target, Shopify, Google) in any core specification or documentation.
*   **DO** use role-based terms: `Merchant`, `Provider`, `Agent`, `Buyer`, `Participant`.

### 2. Protocol Architecture
*   **Agnosticism:** Ensure all new constructs (e.g., extensions, mandates) are not tied to any single organization's business logic.
*   **Consistency:** New features must align with the definitions in the `00-glossary.md` or equivalent core documentation.

### 3. Documentation Integrity
*   **MkDocs Compliance:** Ensure all Markdown files follow the expected structure for the MkDocs build (configured in `mkdocs.yml`).
*   **Cross-Links:** Use absolute GitHub URLs when linking to other repositories in the UCP ecosystem.

## Technical Standards

### Documentation Style
*   **Formatting:** Enforced via Prettier (2-space indentation).
*   **Line Length:** Hard-wrap prose at **80 characters** for maximum readability in all environments.
*   **Tables:** Use consistent formatting for API request/response tables.

### Python Hooks (Automation)
*   **Linter:** Ruff (configured for **2-space indentation** in `pyproject.toml`).
*   **Docstrings:** Google Style docstrings for all automation scripts (e.g., `hooks.py`, `main.py`).

## Semantic Review Focus
Gemini should prioritize:
1.  **Terminology Alignment:** Does the PR use terms as defined in the core protocol glossary?
2.  **Brand Leaks:** Rigorously check for any accidental brand mentions in new documentation.
3.  **Cross-Impact:** Does a change in one specification file impact others unexpectedly?
