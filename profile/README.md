# Ky Suite

**Self-hosted mail, calendar, chat, files and homelab tools with one login and one backup.**

Ky ("Key") is a set of MIT-licensed services you run on your own hardware, VPS or cloud
account. Every product signs in through KyIdentity and backs up to KyRecovery, so you set
those two up once and pair everything else to them. AI features run on your own server, and
encrypted data is never sent to a model.

Made by [Busnes.app](https://busnes.app).

## Start here

1. **[KyIdentity](https://github.com/Busnes-app/KyIdentity-server)**: single sign-on and MFA
   for the whole suite.
2. **[KyRecovery](https://github.com/Busnes-app/KyRecovery-server)**: encrypted, central
   backup and restore, to local disk or R2/S3.
3. Add the products you want and pair each one to both.

## Products

| Product | What it does | Status |
|---|---|---|
| [KyIdentity](https://github.com/Busnes-app/KyIdentity-server) | Identity provider: SSO, TOTP and push MFA | Stable |
| [KyPost](https://github.com/Busnes-app/KyPost-Server) | Email: web client for your IMAP account, or your own mail server. OpenPGP end to end; a local model sorts unencrypted mail. | Stable (own mailboxes: beta) |
| [KyDNS](https://github.com/Busnes-app/KyDNS-server) | DNS blackhole for homelabs, with one-step names and paired replication | Stable |
| [KyRecovery](https://github.com/Busnes-app/KyRecovery-server) | Central encrypted backup and restore for every Ky product and whole containers | Beta |
| [KyCalendar](https://github.com/Busnes-app/KyCalendar) | CalDAV calendars, KyPost appointments, an MCP server for your AI agent | Beta |
| [KyYard](https://github.com/Busnes-app/KyYard-server) | Container fleet management and one-click upgrades | Beta (Docker); Preview (Kubernetes) |
| [KyMessages](https://github.com/Busnes-app/KyMessage-Server) | Team chat and calls on Matrix, using standard Matrix clients | Beta |
| [KyDrive](https://github.com/Busnes-app/kydrive-server) | Files over WebDAV, in-browser office editing, whiteboards | Preview |
| [KyNotes](https://github.com/Busnes-app/KyNotes-server) | End-to-end encrypted notes with text and canvas | Preview |
| [KyPulse](https://github.com/Busnes-app/KyPulse-server) | Health and monitoring across Ky products | Preview |
| [KyQuickStart](https://github.com/Busnes-app/KyQuickStart) | Deploy the Ky products you choose in one step | In development |

**Stable** means the maintainer runs it every day. **Beta** works but needs more testers.
**Preview** is early: expect rough edges.

## Apps

- **KyAuth** (KyIdentity push approvals): [iOS](https://github.com/Busnes-app/KyAuth-iOS),
  [Android](https://github.com/Busnes-app/KyAuth-android),
  [Linux phones](https://github.com/Busnes-app/KyAuth-Linux)
- **KyPost**: [iOS](https://github.com/Busnes-app/KyPost-for-Mac),
  [Android](https://github.com/Busnes-app/KyPost-for-Android),
  [Linux phones](https://github.com/Busnes-app/KyPost-for-Linux)

## Shared code

[ky-primitives](https://github.com/Busnes-app/ky-primitives) (Go security primitives),
[ky-server-base](https://github.com/Busnes-app/ky-server-base) (the scaffold every Ky server is built from),
[ky-ui](https://github.com/Busnes-app/ky-ui) (shared web theme).

## Help and contributing

Found a bug? Open an issue on the product's repository. Report security problems privately,
as described in the [security policy](https://github.com/Busnes-app/.github/blob/main/SECURITY.md).
Anything else: hello@busnes.app.
