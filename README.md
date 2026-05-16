  git push
-->

# Hezarfen Vault — An AI-Native Knowledge Base for Solo Clinical Researchers

> Built by [Onour Impram (Hezarfen)](https://github.com/TheGoatPsy), licensed clinical psychologist in Türkiye, Greece, and Ireland, PhD candidate in Clinical and Health Psychology at Istanbul University, author of "Üretken Yapay Zekâ ve Ruh Sağlığı" (Nobel Academic Publishing, 2026).

A production-grade Claude Code infrastructure for a solo clinical practitioner who is simultaneously running clinical practice, doctoral research, university lecturing, AI safety research, and a 21-app + 20-game indie portfolio. This repository documents the architecture, lessons learned, and reusable patterns.

## Why this exists

Most "AI for clinicians" content assumes you are using ChatGPT or a hosted EHR plugin. This repository documents what happens when a clinical psychologist with a multi-country practice builds their own **production-grade local-first AI infrastructure** instead. The result is a single-developer system that touches:

- Clinical case formulation (privacy-preserving, GDPR-aligned)
- Academic manuscript pipeline (APA 7, citation verification, journal targeting)
- Multi-jurisdiction legal compliance (TR + EL + IE + EU AI Act)
- Token economics (330M tokens saved via custom RTK pipeline)
- Indie app/game development (21 apps + 20 casual games)
- Personal memory consolidation (orphan-prevention rituals)

## Architecture at a glance

```
~/.claude (junction) → Hezarfen-Vault/.claude/   (Obsidian brain layer)
~/.rtk    (junction) → Hezarfen-Vault/06-Altyapi/rtk-home/
~/.omc    (junction) → Hezarfen-Vault/06-Altyapi/omc-home/
~/.claude-code-router → Hezarfen-Vault/.claude-code-router/

Hezarfen-Vault/
├── .claude/                 # Canonical Claude home (vault-rooted)
│   ├── skills/              # 197 user-level skills
│   ├── plugins/             # 23 marketplaces, 342 plugins
│   ├── commands/            # 53 custom slash commands (TR + EN)
│   ├── agents/              # 8 sub-agents for academic workflow
│   ├── hooks/               # 11 hook scripts (settings.json driven)
│   └── projects/            # 949+ session transcripts (Hezarfen-Vault)
│
└── 06-Altyapi/              # Infrastructure layer
    ├── Hafiza-Sistemi-2-0/  # Custom Python memory system (14 scripts)
    │   ├── session_end_ritual.py    # 8-step orphan prevention (Stop hook)
    │   ├── frontmatter_validate_hook.py
    │   ├── vault_write_post_hook.py
    │   └── ...
    ├── claude-cookbooks/    # Anthropic Managed Agents cookbook clone
    ├── scripts/             # install-stack + finalize-vault-migration + verify
    └── Claude-Code-Ecosystem-Entegrasyon/
        ├── Master-Plan-2026-05-16.md
        ├── Microsoft-365-Add-ins.md
        ├── Managed-Agents-Cookbook-Quickstart.md
        └── Recovery-Setup-New-Machine.md
```

## What makes it elite tier

Per a self-assessment audit performed during deep maintenance (2026-05-16):

| Dimension | Score |
|---|---|
| Custom infrastructure depth | 9.5 / 10 |
| Multi-domain integration | 9.5 / 10 |
| Token consciousness | 9.0 / 10 |
| Plugin breadth | 9.0 / 10 |
| Personal-fit | 9.5 / 10 |
| Architectural coherence | 8.5 / 10 |
| Discoverability | 6.0 / 10 (improving via this repo) |
| **Overall** | **8.5 / 10** |

The architecture sits in the top 0.1% of Claude Code setups primarily because:

1. **Custom Python memory layer** (Hafıza-Sistemi-2-0) with deterministic orphan prevention, frontmatter validation at write time, and an 8-step session-end ritual driven by Claude Code Stop hooks.
2. **Junction-based vault canonical architecture** — `~/.claude` is a Windows junction to the vault root, making the Obsidian brain and Claude Code home the same source of truth.
3. **Multi-domain skill stack rare in one user**: clinical psychology + GDPR/EU AI Act legal + APA 7 academic + casual game development + token optimization.
4. **Turkish language domain customization**: `hezarfen` output style, 13 Turkish slash commands, brand voice configuration.
5. **Three-layer token consciousness**: RTK CLI proxy (333M lifetime savings) + token-optimizer plugin + on-demand caveman mode.

## ACoR-P — Algorithmic Co-Regulation Principles

The vault is the operational expression of the **ACoR-P framework** (preprint forthcoming on PsyArXiv), which defines five constructs for ethical AI use in clinical mental health practice:

1. **Algorithmic transparency** — every AI-generated artifact carries provenance metadata
2. **Clinical accountability gates** — no AI output reaches a patient without a clinician sign-off step
3. **Co-regulation hooks** — the system enforces boundaries via deterministic Python pre/post hooks
4. **Patient data isolation** — strict separation between personal/research/clinical vaults
5. **Regulatory alignment** — EU AI Act, Turkish Sağlık Bakanlığı, Irish HIQA, Hellenic Ministry of Health

The Hafıza-Sistemi-2-0 layer is the technical implementation of ACoR-P principle #3 (co-regulation hooks).

## What is open-sourced here

This repository is a **public showcase**, not the live vault (which contains personal/clinical data). What you'll find:

- Architecture documents (anonymized)
- Hafıza-Sistemi-2-0 Python scripts (extracted, generic)
- Claude Code configuration templates
- Slash command authoring guide (Turkish-first)
- Skill index (1,888 cached → 1,268 visible)
- ACoR-P framework documentation

What you'll **not** find (intentionally):

- Actual settings.json with secrets
- Personal vault content (notes, sessions, clinical materials)
- Anything that would compromise patient confidentiality

## How to reproduce

1. Read [Recovery-Setup-New-Machine.md](docs/Recovery-Setup-New-Machine.md)
2. Adapt `install-stack.ps1` to your environment
3. Replace `Hezarfen-Vault` paths with your own
4. Cherry-pick the bits you actually need (Hafıza-Sistemi-2-0 Python layer is the most reusable)

## Anthropic open-source contributions (planned)

As part of the broader ecosystem work, contributions to upstream Anthropic repositories are queued:

- `anthropics/skills` — Turkish academic writing skill with APA 7 enforcement
- `anthropics/claude-plugins-community` — `clinical-mental-health-safety` plugin packaging the ACoR-P principles
- `anthropics/claude-cookbooks` — `psychology_research_managed_agent.ipynb` for headless clinical research workflows
- `anthropics/claude-for-legal` — Turkish health-sector regulatory gap checker
- `anthropics/life-sciences` — Mental health-specific clinical decision support extension

## Selected sub-agent roster

| Agent | Purpose |
|---|---|
| `application-tracker` | Track and follow-up on academic and grant applications |
| `cover-letter-generator` | APA-aligned cover letter drafting (journal targeting) |
| `feedback-delta-updater` | Compute delta between reviewer rounds |
| `fit-scorer` | Score paper-journal fit |
| `literature-reviewer` | Multi-database systematic search (PubMed, Wiley, Consensus) |
| `paper-miner` | Extract writing patterns from corpus |
| `rebuttal-writer` | Reviewer rebuttal drafting with rigor preservation |

## Selected Turkish slash commands

- `/oturum-kapat` — Session close ritual (8-step orphan prevention)
- `/vault-ara` — Natural language search across vault (BM25-lite + LEANN)
- `/celiski-bul` — Find contradictions across vault notes
- `/cross-alan-fikir` — Cross-domain ideation across the five vault domains
- `/kavram-evrim` — Temporal evolution of a concept across vault history
- `/gunluk` — Daily journal entry creator
- `/wiki-compile` — Compile raw notes into thematic wiki pages

## Selected lessons

From [tasks/lessons.md](tasks/lessons.md):

- **Canonical .claude location is in the vault root**, not under `06-Altyapi/` (a recovery from a folder-move incident taught this).
- **Windows Python alias bash regression**: `~/bin/python.cmd` shims work in PowerShell but Git Bash needs extensionless `python` and `python3` files with `#!/bin/bash` shebangs.
- **Robocopy /XO direction trap**: newer source files overwrite older destinations, which clobbered a comprehensive settings.json with a minimal one during a merge.

## Hire me

If you are at Anthropic or an aligned organization working on **AI safety in clinical mental health**, **constitutional AI for sensitive contexts**, or **regulatory alignment of frontier AI in healthcare**, the operator of this vault is open to conversations.

- Email: onurb693@gmail.com
- LinkedIn: [Onour Impram](https://www.linkedin.com/in/onour-impram/)
- Academic profile: [Istanbul University](https://psikoloji.istanbul.edu.tr/)

## License

MIT (this repository) — feel free to fork the patterns. The live vault remains private.
