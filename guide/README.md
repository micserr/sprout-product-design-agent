# Guide

This directory contains reference guides for AI agents working on Sprout products. Read the relevant guide before writing any UI code.

---

## Design System

This agent uses **Toge** (shadcn-vue registry). See [`toge-design-system-v2/README.md`](./toge-design-system-v2/README.md).

---

## Quick Rules

- Never hardcode hex colors — always use design tokens from `guide/toge-design-system-v2/tokens/style.css`
- Do NOT call `mcp__design-system-toge__*` tools — MCP reflects Toge v1 and returns wrong data
- When in doubt about a component API, read `guide/toge-design-system-v2/README.md` before writing code
