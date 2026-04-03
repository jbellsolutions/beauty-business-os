# Genome — What This Is

This repo participates in the AGI-1 genome system. The genome is a shared knowledge base that lives at `~/.claude/agi-1-genome/genome.json` on the developer's machine.

## What It Does

- **Healing patterns** — When the AI encounters an error it has seen before (in this repo or any other), it can fix it automatically using patterns from the genome.
- **Instruction improvements** — Best practices learned from working on other repos are inherited here.
- **Anti-patterns** — Known mistakes are flagged before they happen.

## What It Does NOT Do

- It does not send data to any external service
- It does not share business data or client information
- It only stores technical patterns about code/repo structure
- It lives entirely on the local machine

## Privacy

The genome is a local JSON file. Nothing leaves the machine unless the developer explicitly shares it. The `sharing.json` file in the genome directory controls opt-in sharing preferences.
