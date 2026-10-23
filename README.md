# Skillfoundry · False Dawn Industries

A three-gate audit framework that turns any piece of content into a scored,
evidence-checked asset: **Relevance → Performance → Signal**, held together by a
single audit contract that emits a machine-validated report.

The gates ship as portable agent skills (agent-skills.io spec — the same format
Claude Code, Hermes, and Replit Agent read). Drop the `skills/` directory into
your agent's skill folder and the gates become callable.

## The three gates

1. **relevance-gate** — the Market-Deficit Analyzer. Scores whether an asset
   solves a specific job-to-be-done for a defined audience, or is just
   impression-farming noise. Built on Christensen's Jobs-to-be-Done.
2. **performance-gate** — the Enterprise Value Test. Scores whether the work
   produces measurable business outcomes, not applause.
3. **signal-gate** — the Adversarial Defense pass. Attacks the asset the way a
   hostile reader, a competitor, or an AI answer engine would, and scores what
   survives.

**shared-audit-contract** — the single output contract every gate conforms to:
a fixed finding schema, scoring rubric, and report format, with a validator
(`scripts/validate-report.mjs`) and a worked example audit in `references/examples/`.

## Install

Copy (or symlink) any gate into your agent's skills directory:

    cp -r skills/relevance-gate ~/.claude/skills/
    cp -r skills/shared-audit-contract ~/.claude/skills/

Run the report validator on any audit output:

    node skills/shared-audit-contract/scripts/validate-report.mjs report.json

## What this is not

This repository is the audit framework — the three gates and their shared
contract. The SkillFoundry marketplace platform (agent training marketplace,
billing, MCP server) is a separate, proprietary False Dawn Industries product
and is not included here.

## License

MIT — see LICENSE.
