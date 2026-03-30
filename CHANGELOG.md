# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.3.0] - 2026-03-24

### Added
- `ui-polish` skill — Phase 6 of the design agent workflow covering typography, surfaces, animations, and performance
- Phase 6 UI Polish to product design agent orchestrator
- `CODE_OF_CONDUCT.md` and `CONTRIBUTING.md`
- `CHANGELOG.md`

### Changed
- Toge v2 installation guide rewritten from official source (`github.com/Aiah-Ai/toge-ds-components`)
- `performance.md` in ui-polish made framework-agnostic (React + Vue examples)
- Wireframe bento card constraint updated to include `border border-gray-100`

## [0.2.0] - 2026-03-23

### Added
- Stack discovery (Phase 3→4 transition) — auto-detects Toge v1 vs v2 from `package.json` and `components.json`
- Stack context header (`// Stack: ...`) written as first line of every prototype
- Pre-flight check (Step 0) in prototype skill — 4 agnostic failure pattern checks
- `guide/toge-design-system-v2/tokens/token-mapping.yaml` — default Tailwind → Toge token substitution map

### Changed
- Toge v2 token enforcement updated in prototype skill and agent
- Guide paths updated throughout after directory rename

## [0.1.0] - 2026-03-22

### Added
- Initial skills: `ux-market-research`, `problem-framing`, `user-journey`, `wireframing`, `prototype`, `design-tokens`, `design-qa`
- Product design agent with dual-mode (Advisor + Orchestrator) and 5-phase workflow
- Guide directories for Toge v1 (`design-system-next`) and Toge v2 (shadcn-vue registry)
- Adapters for Claude Code, Codex CLI, Cursor, and BMAD
- `install.sh` for multi-framework installation

### Changed
- Renamed "Sprout Legacy" → "Toge v1" and "Toge" → "Toge v2" across all files
- Added `toge:` prefix to `wireframing` and `prototype` skill names
- Repo renamed to `sprout-design-agent`

[Unreleased]: https://github.com/micserr/sprout-design-agent/compare/v0.3.0...HEAD
[0.3.0]: https://github.com/micserr/sprout-design-agent/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/micserr/sprout-design-agent/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/micserr/sprout-design-agent/releases/tag/v0.1.0
