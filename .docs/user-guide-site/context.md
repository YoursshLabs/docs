# Context

- The repo was created from Mintlify's hosted starter ("Initial commit from Mintlify hosted docs"), so a Mintlify project is connected to it.
- Static export (`mint export`) is Enterprise-only, so self-hosting on GitHub Pages is not an option. CI therefore validates the build and triggers the hosted deployment through the Mintlify API (`POST /v1/project/update/{projectId}`, then poll `GET /v1/project/update-status/{statusId}`: queued | in_progress | success | failure | skipped).
- Screenshots: 209 PNGs from the app repo's `tool/docs_journey.sh` run at v0.4.0 (demo containers, isolated HOME); the mobile pair QR was re-encoded to 192.0.2.10.
- Old content: app repo `docs/wiki/User-Guide-*.md`, `Developer-Guide-*.md`, `docs/SYNC_SETUP.md`, `docs/plugin-authoring-guide.md`.
