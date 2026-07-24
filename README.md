# GHL Product Intelligence Dashboard — Published Site

This repo contains ONLY the publicly-hostable, passphrase-encrypted build of
the dashboard (docs/index.html). It intentionally does NOT contain any of the
raw knowledge_base/, reports/, or memory/ files from the main project — those
stay local-only.

docs/index.html is regenerated daily by the AI CPO Assistant agent by running
publish.js against the freshly-built reports/command_center.html, then
committed and pushed here so GitHub Pages picks up the new version
automatically.

The page is gated by a client-side AES-256-GCM passphrase lock — the
encrypted data ships in the file, but is unreadable without the passphrase
(derived via PBKDF2, 250k iterations). Nobody with just the URL can read the
underlying data.
