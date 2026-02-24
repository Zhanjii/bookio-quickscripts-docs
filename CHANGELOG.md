---
layout: default
title: Changelog
nav_order: 5
---

# Changelog

All notable changes to BookIO QuickScripts will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [6.0.7] - 2026-02-23

### Added
- Add /keyboard-shortcuts command
- Add git_guard.py for destructive command blocking
- Add /claude-updates skill for tracking Anthropic changes
- Add demand intelligence enhancements to Book Profiler

### Changed
- Bump version to 6.0.7 for release
- Sync from templates — generate-plan, claude-updates, remove stale review-codebase
- Remove stale codebase-section-reviewer agent
- Sync: Add affordance mapping pattern from templates
- Sync: Update CLAUDE.md with PROJECT-SPECIFIC markers and sync commands
- Update Anthropic model list and doc URLs
- Remove outdated v6.0.5 spec file
- Bump version to 6.0.7.dev for development

### Fixed
- Address 38 review findings in Book Profiler

## [6.0.6] - 2026-02-16

### Added
- Push admin password changes to remote config repo
- Add Cover Crop tab, review fixes for cover tabs, and low-credit warning
- Add Cover Extend tab with AI outpainting for title-safe covers
- Add book similarity matching engine with Find Similar button
- Add Book Profiler tab with hierarchical AI analysis pipeline

### Changed
- Bump version to 6.0.6 for release
- Update build scripts, radar chart, and docs for Book Profiler
- Update review commands and add execute-review-fixes
- Switch docs to Just the Docs theme with dark mode
- Bump version to 6.0.6.dev for development

### Fixed
- Persist activation PIN and admin role across app restarts
- Restore folder_templates.json and add self-healing for missing categories
- Bundle all dependencies in macOS/Windows build scripts
- Add cryptography to collect_all in all build scripts
- Review pass 5 — 29 fixes across 8 categories + platform packaging docs
- Skip CI tests on version tags and preserve activation across upgrades

## [6.0.5] - 2026-02-11

### Added
- Add live cover preview canvas to Zip Creator tab
- Auto-push configs to remote repo when saving in admin mode
- Add ban sticker tags (BAN, AUDIOBAN, BLACKROCK) to zip_tags config
- Add logo image integration for blockchains, companies, and stickers
- Mode-aware title bar styling for all dialogs + CTkMessagebox migration
- Replace OS color picker with CTkColorPicker
- Add drag-and-drop tab reordering and simplify settings tabs
- Make theme list dynamic; fix flaky CI benchmark
- Add CTk color theme selection with 19 themes
- Add appearance mode setting (Dark / Light / System)
- Centralize all hardcoded colors into colors.py and add orange theme
- Admin/user role-aware UI, config sync, and cross-date project matching
- Add automatic GitHub issue creation for crash reports

### Changed
- Release: v6.0.5 — cover preview, 19 themes, tab drag-drop, 4 review passes
- Test+docs: Add zip creator tests (150) and cover preview documentation
- Add 7 specialized review agents, commands, and /review-all orchestrator
- Targeted reviews — thread safety, atomicity, resource leaks, performance, dead code
- Codebase review, security hardening, and config access unification
- Restore dmg background image for mac
- Project cleanup — remove stale files, notes, and build artifacts
- Remove unused deps and deduplicate config sync boilerplate
- Tech debt reduction — remove dead code, split god files, add debug logging
- Gitignore remote-synced config JSONs and action-plans
- Set plansDirectory to action-plans in settings
- Update sync commands and add template markers to CLAUDE.md
- Add bookio and fintech theme files
- Replace last 10 hardcoded colors with C constants
- Final sweep — replace 23 more hardcoded colors with C constants
- Remove working docs from repo
- Replace remaining hardcoded colors with C constants across 25 files
- Consolidate colors.py from 44 to 32 constants
- Remove working audit file from repo
- Optimize CLAUDE.md and update .gitignore
- Add *.json.backup to .gitignore and untrack config backup files
- Sync list_todos.py with claude-code-templates repo
- Fix all flake8 errors — 461 issues resolved to zero
- Full lint cleanup — mypy, black, isort all passing with zero errors
- Sync commands, scripts, and config from templates repo
- Sync commands and CLAUDE.md from templates repo
- Bump version to 6.0.5.dev0 for next dev cycle

### Improved
- Optimize settings dialog Templates and YouTube Links tabs

### Fixed
- Track bundled config files and sync folder_templates from remote
- Guard against None stdout in --windowed PyInstaller builds
- Force app window to foreground on launch and validate screen bounds
- Use standalone CTk window for activation dialog on all platforms
- Force activation dialog to foreground in windowed exe mode
- Google OAuth token resolution and non-blocking authorize flow
- Review pass 4 — thread safety, crash bugs, resource leaks, performance, dead code, security, and logic bugs
- Disable error reporter in tests and fix test suite failures
- Theme change full UI rebuild and image loading improvements
- Fix 17 silent logic bugs found by targeted review
- Execute 7 review reports pass 3 — ~37 fixes, ~2,396 net lines removed
- Execute 7 review reports pass 2 — ~114 fixes, ~1,477 net lines removed
- Execute 7 codebase review reports — ~80 fixes, ~2,850 lines dead code removed
- Protect master encryption key chain from security review modifications
- Eliminate 3 CRITICAL performance UI freeze issues
- Prevent recurring API key loss and blockchain reappearance
- Uniform transparent backgrounds for tabs and fix theme-switch tab click bug
- Recreate menu bar during theme rebuild to prevent stale dropdowns
- Relax image resize performance threshold for CI runners
- Allow claude_format.py to accept file paths as CLI arguments
- Guard against darkdetect crash on macOS for CustomTkinter apps
- Patch _slack_sdk_available in test to properly simulate missing SDK
- Quote tk.Event[Any] annotations for Python 3.10/3.11 compatibility
- Fix DEAs folder name missing media type for non-prefixed media types

## [6.0.4] - 2026-01-19

### Added
- Add encrypted remote config with admin controls and remove legacy format
- Add development mode to prevent accidental config pushes

### Changed
- Release: v6.0.4 production build with remote-only admin auth
- Add migration tool, remote config tab, and technical spec
- Add TODO finder command and clean up CLAUDE.md
- Restore production folder templates and add clean-images command
- Remove coverage minimum threshold
- Move DMG background image to dedicated folder
- Add DMG background image to project root

### Improved
- Optimize GUI tests with mocks and add cross-platform CI

### Fixed
- PIN persistence on restart and empty media type in zip filenames
- Ensure API config persists to AppData, not MEIPASS temp directory
- Increase performance test thresholds for CI
- Add tkinter mock to session manager roundtrip test
- Fix 3 pre-existing test failures
- Include GUI tests in main test run
- Update development mode tests for new .dev version check
- Restore cross-platform CI testing (Windows, macOS, Ubuntu)
- Remove non-existent package and simplify CI to Windows-only
- Use PEP 440 compliant version format for development mode

## [6.0.3] - 2026-01-08

### Added
- Add auto-download updates with deferred installation
- Add year rotation manager for automatic folder creation
- Add system tray integration with minimize-to-tray support
- Add auto-generated changelog from git commits
- Add About dialog, public docs, and GitHub Pages integration
- Add crash/error reporting and session restore features
- Add View Changelog action plan and update menu bar plan

### Changed
- Remove duplicate and placeholder test files
- Revert "chore: Clean up unused files and update test configurations"
- Clean up unused files and update test configurations
- Reorganize test suite and fix test infrastructure
- Release v6.0.3
- Stop tracking local Claude settings file
- Add local settings and images to gitignore
- Add Claude Code configuration and move year rotation docs
- Update app settings and UI components
- Move completed action plans to old folder and add update manager tests
- Enhance Check for Updates with config refresh and status detection
- Update About dialog status and document DOCS_DEPLOY_TOKEN
- Move implemented action plans to old folder

### Fixed
- Make tests cross-platform compatible (macOS/Windows/Linux)
- Hide system tray settings on macOS where tray is disabled
- Resolve test deadlock and improve test infrastructure
- Repair broken tests and add auto-exclusion for test folders
- Reduce macOS keychain password prompts to single prompt
- Improve Windows taskbar icon loading with multiple fallback methods
- Simplify taskbar icon loading using external path
- Extract taskbar icon from EXE itself instead of temp path
- Prioritize user API config over bundled config in EXE
- Improve Windows taskbar icon loading with ExtractIconW fallback
- Bundle icons and changelog in EXE, fix changelog loading
- Correct test failures in logging and validation tests
- Fix error reporter to fetch app_access config directly from GitHub

## [6.0.2] - 2025-12-26

### Changed
- Initial commit - v6.0.2 codebase

---

## Version History Summary

| Version | Date | Highlights |
|---------|------|------------|
| 6.0.7 | 2026-02-23 | Bump version to 6.0.7 for release, Sync from templates — generate-plan, cla, Remove stale codebase-section-reviewer a |
| 6.0.6 | 2026-02-16 | Bump version to 6.0.6 for release, Push admin password changes to remote co, Persist activation PIN and admin role ac |
| 6.0.5 | 2026-02-11 | Track bundled config files and sync fold, Guard against None stdout in --windowed , Force app window to foreground on launch |
| 6.0.4 | 2026-01-19 | Release: v6.0.4 production build with re, PIN persistence on restart and empty med, Add migration tool, remote config tab, a |
| 6.0.3 | 2026-01-08 | Make tests cross-platform compatible (ma, Hide system tray settings on macOS where, Resolve test deadlock and improve test i |
| 6.0.2 | 2025-12-26 | Initial commit - v6.0.2 codebase |
