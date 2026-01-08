# Changelog

All notable changes to BookIO QuickScripts will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
| 6.0.3 | 2026-01-08 | Make tests cross-platform compatible (ma, Hide system tray settings on macOS where, Resolve test deadlock and improve test i |
| 6.0.2 | 2025-12-26 | Initial commit - v6.0.2 codebase |
