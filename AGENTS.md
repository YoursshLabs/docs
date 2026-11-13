# YourSSH documentation — instructions for writers and agents

## About this project

- The documentation site for [YourSSH](https://github.com/YoursshLabs/yourssh), built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter (`title`, `description`, optional `icon` from Lucide/Font Awesome).
- Configuration and navigation live in `docs.json`. A page that is not listed there is not published.
- Preview: `npx mint dev`. Before a pull request: `npx mint validate` and `npx mint broken-links` (CI runs both).
- Screenshots live in `images/<NN-section>/<NN-step>.png`. They come from the app repo's isolated docs journey (`tool/docs_journey.sh` in YoursshLabs/yourssh) and are resized to at most 1440 px wide. Reuse those names; don't add screenshots of real servers, real IPs or real user data.

## Terminology

- **YourSSH** (one word, capital Y, S, S, H). "The app" is fine after the first mention.
- **Host**: a saved connection profile (SSH, RDP or VNC). Not "server" when you mean the saved profile.
- **Session** / **tab**: a connected terminal, RDP or VNC view in the top tab bar.
- **Hosts dashboard**: the Home screen with group cards and host cards.
- **Host editor**: the side panel that opens from **New host** or **Edit**.
- **Connection chain**: jump hosts (bastions) in front of a host. Not "proxy jump" in headings.
- **Keychain**: the SSH key manager screen. The macOS Keychain / Windows Credential Manager is the **system credential store**.
- **Known hosts**: pinned host keys. **Host key**: the server's SSH key. Don't call it a fingerprint unless you mean the SHA-256 string.
- **Plugins**: built-in plugins (Snippets, DevOps Hub, Web Tools) and script plugins (JavaScript in `~/.yourssh/plugins`).

## Style

- Active voice, second person ("you"), present tense. One idea per sentence.
- Sentence case for headings and titles.
- Bold for UI labels exactly as the app shows them: click **New host**, then **Save**.
- Code formatting for file names, paths, commands, keys and settings values: `~/.ssh/config`, `Ctrl+Shift+I`.
- Keyboard shortcuts: show macOS first, then Windows/Linux when they differ (`Cmd+K` / `Ctrl+K`).
- Use Mintlify components where they help: `<Steps>` for procedures, `<Note>`/`<Tip>`/`<Warning>` sparingly, `<Frame>` around screenshots with a short caption, `<CardGroup>` on overview pages, `<Tabs>` for per-OS instructions.
- Every screenshot has meaningful alt text.
- Document what the app does today. If you're unsure whether a feature exists or how it behaves, check the app repo (`CLAUDE.md`, `app/lib`) instead of guessing.

## Content boundaries

- User guide: what a user sees and does, plus the security behaviour they need to understand (host key pinning, credential storage, what syncs and how it's encrypted).
- Developer guide: building from source, architecture, plugin system and plugin authoring.
- Don't document internal process docs (`docs/superpowers/` in the app repo), unreleased features or roadmap items as if they shipped.
