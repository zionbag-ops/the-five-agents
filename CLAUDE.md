# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

"The Five Agents" is a TypeScript/Node.js project. Source files have not been added yet — update this file once the codebase takes shape.

## Stack

- Language: TypeScript
- Runtime: Node.js

## Mandatory Agent Routing

For every task in this project, delegate to the CEO agent at `.claude/agents/ceo.md`.
The CEO will analyze the task and route it to the appropriate sub-agent(s).

Do not bypass the CEO and call sub-agents directly.

## Vault Workflow (Mandatory)

At the **start of every task**, follow the obsidian-vault-workflow skill defined in `.claude/skills/obsidian-vault-workflow/SKILL.md`:
1. Identify the topic, locate its file in `vault/Meeting Notes/`, read it fully if it exists.
2. Read the 2–3 most recent entries in `vault/Meeting Notes/`.
3. State in one sentence what context was loaded before writing any code.

At the **end of every task**, append a dated Session Log entry to the relevant topic file in `vault/Meeting Notes/`.

## Claude Code Configuration

Project-level Claude Code settings live in [.claude/settings.json](.claude/settings.json).
Custom slash commands for this project go in [.claude/commands/](.claude/commands/) as `.md` files.
