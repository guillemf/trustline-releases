# Trustline

A desktop application for engineering managers. It keeps the record of the
one-to-ones you hold, the trust you have actually earned with each person, and
the career path each of them is on — on your own machine, in ordinary files,
with no account and no server.

Trustline follows the team-management chapter of
[*The Engineering Protocol Stack*](https://engineeringprotocolstack.com/book/).
It is free, for macOS, Windows, and Linux.

**This repository distributes the installers only — it holds no source code.**
The application is proprietary; see [Licence](#licence) below. The product page,
with the full description and the download buttons, is at
[engineeringprotocolstack.com/tools/trustline](https://engineeringprotocolstack.com/tools/trustline/)
([en español](https://engineeringprotocolstack.com/es/tools/trustline/)).

## Download

Current version: **0.2.0**. Every version, with its release notes, is listed
under [Releases](https://github.com/guillemf/trustline-releases/releases).

| Platform | Download | Requirements |
| --- | --- | --- |
| macOS | [Trustline_0.2.0_universal.dmg](https://github.com/guillemf/trustline-releases/releases/download/v0.2.0/Trustline_0.2.0_universal.dmg) · 13.5 MB | Universal — Intel and Apple silicon |
| Windows | [Trustline_0.2.0_x64-setup.exe](https://github.com/guillemf/trustline-releases/releases/download/v0.2.0/Trustline_0.2.0_x64-setup.exe) · 4.8 MB | Windows 10 or later · 64-bit |
| Linux | [Trustline_0.2.0_amd64.AppImage](https://github.com/guillemf/trustline-releases/releases/download/v0.2.0/Trustline_0.2.0_amd64.AppImage) · 88 MB | x86_64 · Ubuntu 22.04 or newer and equivalents |
| Linux · Debian | [Trustline_0.2.0_amd64.deb](https://github.com/guillemf/trustline-releases/releases/download/v0.2.0/Trustline_0.2.0_amd64.deb) · 10.7 MB | Debian 12+, Ubuntu 22.04+, and derivatives |

Prefer the `.deb` on any Debian-derived distribution. The AppImage is eight
times larger for the same application because it carries its own copy of the
WebKitGTK rendering engine; the `.deb` declares that engine as a dependency and
lets your package manager supply it.

Versions from 0.2.0 onward ask this repository once a day whether a newer
release has been published, and say so in the app if one has. The request sends
nothing about you, and Preferences → About can turn it off. Earlier versions do
not check; watching this repository's releases — or the product page, which
always names the current version — is how to find out that a new one exists.

### The first launch needs one extra step

These builds are not yet signed with a paid developer certificate, so macOS and
Windows will both warn that the publisher cannot be verified. What that warning
means in practice is that the operating system can see the file carries no
certificate it recognises — not that it found anything wrong with it.

- **macOS** — right-click the app and choose *Open*, then confirm once. Opening
  it by double-click the first time will not offer that choice.
- **Windows** — choose *More info*, then *Run anyway*.
- **Linux** — no warning, but an AppImage has to be made executable before it
  will run: `chmod +x Trustline_0.2.0_amd64.AppImage`.

Certificates are being obtained, and these warnings will disappear in a later
release.

## What it does

- **One-to-one sessions.** A structured record of every one-to-one — what was
  discussed, what was agreed, and what is still open — so the next session
  starts where the last one ended instead of from memory.
- **Trust, tracked honestly.** Trust is the currency a manager actually spends.
  Trustline asks you to state where it stands with each report and keeps the
  history, which makes a slow decline visible while it is still fixable.
- **Career path canvas.** Place every report on a visual career path, group them
  by team or level, and see the whole shape of your organisation's growth on one
  canvas instead of in a spreadsheet nobody opens.
- **Reports you can hand over.** Export the career path as a PDF to take into a
  calibration meeting, a promotion committee, or a conversation with your own
  manager. Individual sessions export as Markdown or PDF.
- **Teams and documents.** Group reports into teams and keep the documents that
  belong to each — charters, on-call rotations, working agreements — beside the
  people they apply to.
- **Email from your own accounts.** Send an agenda, or collect proposed topics,
  through mail accounts you configure yourself.

## Where your data lives

Trustline has no account, no sign-up, and no backend. The subject matter is
private notes about identifiable people, which is the strongest possible
argument against keeping it on someone else's computer.

Your notes are ordinary files under your own user directory:

| | |
| --- | --- |
| macOS | `~/Library/Application Support/trustline` |
| Windows | `%APPDATA%\trustline` |
| Linux | `~/.local/share/trustline` |

Inside it, `reports.json` and a `sessions/` directory holding one Markdown file
per one-to-one — readable, greppable, and yours to back up however you already
back up your files. Career-path data is kept separately and can be pointed at a
shared or synced folder, so a team can agree on one set of positions while each
manager's own session notes stay private. Both locations are changeable in
Preferences.

Mail-account credentials go to your operating system's keychain — never to a
file on disk. The only servers the application contacts are the mail accounts
you enter yourself and, once a day, GitHub — to ask whether a newer version has
been published. That request sends nothing about you or your notes, and you can
turn it off. Nothing is synced, nothing is analysed, and there is no telemetry
of any kind.

## Licence

Trustline is proprietary software, offered free of charge. It is **not** open
source. From [`LICENSE`](LICENSE), the agreement the installers above are
distributed under:

> You may install and use it; you may not redistribute it. The only party
> permitted to distribute Trustline is its author.

Paid features may be added in future releases. What is free today stays free.

Copyright © 2026 Guillem Fernandez. All rights reserved.

## Links

- [Trustline product page](https://engineeringprotocolstack.com/tools/trustline/)
- [*The Engineering Protocol Stack*, the book](https://engineeringprotocolstack.com/book/)
- [Report a problem](https://github.com/guillemf/trustline-releases/issues)
