# Changelog

## Chat+ 1.2.0

- Apply the owner's approved visual profile: transparent menu themes, button colors/borders, independent free toolbar positions, fluid chat animation, lightweight player cards, bubble height and timestamp/counter colors.
- Enable both name-mention styling and the Minecraft bit notification sound by default. Keep the export's precise styling, sound volume, pitch and cooldown.
- Initialize the eight shared Minecraft chat appearance options once for a genuinely new Chat+ profile, including a transparent chat background. Existing saved profiles and native choices are preserved; Reset uses the same approved factory profile.
- Keep a versioned reference in `docs/defaults/1.2.0.json`, with original export/provenance retained privately. The reference is tested against runtime values; no preset JSON is parsed during normal settings construction/copying.
- Avoid a full component copy for ordinary messages when only mention styling is needed. Preserve native click/hover information, alert/note processing and identity caching.
- Preserve prior releases, personal channels, histories, player data, shortcuts and nonvisual behavior. Existing saved configurations keep their settings.
- Support Fabric Loader 0.19.5+ and the tested Quilt Loader 0.31.0-beta.4 on Minecraft Java 26.3 with the same JAR. Mod Menu is optional; Fabric API is not required.
- Fix missing icons and translations without Mod Menu or Fabric Resource Loader. Register only Chat+'s own resources through the native fallback.
- Reuse custom server-filter regex matchers and clear message references after matching. In the targeted workload, temporary allocations fall by 43.05% compared with 1.1.0, with effectively unchanged processing time.
- With mention styling enabled identically, the new fast path reduces temporary allocations by 46.02% without a mention and 26.86% with a mention versus 1.2.0-beta.1; median processing time falls by about 18.3%. These are microbenchmark results, not whole-client FPS/RAM claims.

39,724 automated checks passed across 64 suites. Fabric 0.19.5 and Quilt 0.31.0-beta.4 were independently verified with and without Mod Menu 21.0.0-beta.1: 466 native checks, 20 targets, 35 resources, 11 rendered screens and the effective factory defaults in each case. Isolated graphical clients used a two-processor test limit and muted audio; these checks do not certify live Microsoft exchanges or audible speech. The owner also reported that the preceding shared beta worked under both loaders. Previous releases remain unchanged.

## Chat+ 1.2.0-beta.1 — local multiplayer test candidate

- One client JAR for Minecraft 26.3, Fabric Loader 0.19.5+ and the tested Quilt Loader 0.31.0-beta.4 target. Quilt stable 0.30.1 does not satisfy the current Fabric-compatibility dependency.
- Fix missing interface textures and native translations when running without Mod Menu or Fabric Resource Loader. A small native fallback registers Chat+'s own resources only; user resource packs keep their normal priority. No additional API or bundled library is required.
- Reuse per-rule regex matchers for custom server filters, clearing message references after every match. Disabled server profiles skip unnecessary custom-pattern compilation.
- In the custom server-filter benchmark against the preserved 1.1.0 JAR, temporary allocations fall by 43.05% (144 bytes per operation). Processing time is effectively unchanged; this is not a whole-client RAM or FPS claim.
- Keep configuration schema, message identity, histories, channel behavior, friends integration and speech settings unchanged.
- Add reproducible, independent Fabric and Quilt candidate checks, with a dedicated optimization review before each installable delivery.
- Preserve all delivered 1.1.0 JARs, source/public bundles and checksums. No publication is performed for this local beta.

The owner will validate authenticated multiplayer, Microsoft friend exchanges and bubble speech. Version-specific reports record the exact test/benchmark results and their limits; automated clients do not certify these live flows.

Testing note: one Fabric + Mod Menu graphical run rendered all screens/assets but encountered a native Windows interruption at shutdown. A targeted two-processor retry exited normally; the cause is not established. The reports retain both observations, and the mod does not impose a CPU limit. This beta awaits normal-profile acceptance testing.

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
