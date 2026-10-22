# Changelog

## Chat+ 1.1.0

### Project links update — 23 October 2026

- Added a compact, collapsible Links panel on the right of Preferences, with project downloads, GitHub, bug reports, suggestions, license and credit links. Small windows keep these links in the scrolling list.
- Added the public GitHub Suggestions category and bilingual suggestion form; bugs remain in Issues.
- Added a Suggestions link to Mod Menu and the proposed English/French Modrinth descriptions.
- Removed the standalone Java installation requirement from player-facing getting-started text. Fabric's technical runtime requirement is unchanged.
- Version remains **1.1.0** at the author’s request. The previous 1.1.0 build is retained in the private recovery backup; version 1.0.0 remains available.

A clearer settings interface, integrated help and lighter message filtering.

### New and improved
- Compact settings tabs with recognizable icons, collapsible sections and persistent navigation.
- Searchable in-game help with examples and a step-by-step channel creation guide.
- An Apply button throughout settings, while keeping the final Save / Discard prompt.
- A shared chat layout editor for colors, dimensions and mouse placement of chat, channel buttons, search and the settings button.
- More consistent and larger previews for chat styling, animations, timestamps, repeated messages, bubbles and player cards.
- Mouse-wheel slider adjustment, with Shift for larger steps, and remembered open/closed sections.
- A factory reset that also restores Minecraft chat appearance while preserving histories, retention limits, notes, ratings and ignored players.

### Fixes and behavior
- Improved channel/alert editors, inline filter controls, separate testing and folded advanced settings.
- Clearer selected-channel feedback and enabled channel/alert rows.
- Improved friends navigation and native cache refresh after relevant actions or foreground changes; Microsoft still controls online-service response times.
- Selective import/export checks cover channel settings/order, server aliases, visual settings, native chat options and player data.
- New/reset mention notifications use `minecraft:block.note_block.bit`. Existing saved preferences remain unchanged.
- Inventory/container theming settings and hooks have been removed. Chat+ and optional game-menu themes remain configurable.

### Performance and maintenance
- Reused regex matching state for channels and alerts, cleared after each message, and fewer temporary membership collections.
- Server-filter caches keep their 4,096-message bound and release peak storage on reset.
- In an internal 16-rule benchmark: channel allocations fell by 92.9% and matching time by 20.8%; alert allocations fell by 97.0% and matching time by 29.3%. These are targeted workload measurements, not FPS or total Minecraft RAM claims.
- Updated licensing notices, icon attribution and public/private release documentation. Logo by **Zaellaa**, created without AI; Font Awesome icons retain **CC BY 4.0**.

### Compatibility
Minecraft Java **26.3**, **Fabric Loader 0.19.5+**, client only. Mod Menu is optional; Fabric API is not required. Keep one Chat+ JAR installed. Existing configuration schema remains compatible.

36,787 automated checks passed, including native Fabric/Mixin loading with and without Mod Menu. Live account services, GPU rendering and audio were not newly certified by these checks.

Bug reports are welcome in **English or French**: https://github.com/DJmush/ChatPlus/issues

Suggestions are welcome in **English or French**: [Suggest a feature](https://github.com/DJmush/ChatPlus/discussions/categories/suggestions).

The previous **1.0.0** release remains available.

[Download 1.0.0](https://github.com/DJmush/ChatPlus/releases/tag/v1.0.0)
