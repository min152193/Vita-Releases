# Privacy

Vita processes audio PCM data in memory. It does not automatically save or upload captured audio.

When the user submits a bug report, Vita sends the report text and these basic fields:

- app version and build
- macOS version
- architecture
- selected source app
- selected output device
- sample rate
- EQ status and preset
- Vitalizer status

When **Include diagnostics** is enabled, Vita also sends up to 200 recent bounded diagnostic events. These events exclude usernames, Apple IDs, file paths, and process lists.

Reports are received by `https://api.sidelabs.net/mac/vita/report`, stored in D1, copied to a private GitHub issue, and announced through a Discord notification. Sparkle uses `https://min152193.github.io/Vita-Releases/appcast.xml` and GitHub release downloads only for software updates.
