# Ky by Busnes.app

**Self-hosted mail, calendars, files, chat, notes and the tools to run them.**

Ky ("Key") is a family of MIT-licensed projects from [Busnes.app](https://busnes.app).
Choose the products you need and run them on your own infrastructure. Many support local
accounts on their own; add KyIdentity for shared sign-in and KyRecovery for sealed backup
storage. Each product documents its required services and recovery coverage.

[Explore the apps](https://busnes.app/apps.html) · [How Busnes.app works](https://busnes.app/how-it-works.html)

## Start with one useful product

1. Pick a product below and follow its README for standalone installation, first sign-in
   and persistent storage. Use the instructions matching the image or source revision you install.
2. Configure its required backends. KyPost needs a mail service; KyDrive staff access needs
   KyIdentity; KyMessages chat needs KyIdentity and the full Matrix stack. Native clients
   need their corresponding server, except KyAuth's local authenticator codes.
3. Add shared sign-in, monitoring and recovery where needed. Verify actual email delivery,
   MFA, access changes and restores separately from setup success or a healthy dashboard.

## Server products

| Product | What it can do | Setup and integration |
|---|---|---|
| [KyIdentity](https://github.com/Busnes-app/KyIdentity-server#readme) | People, groups, application access, OpenID Connect sign-in, MFA and an app launcher. | Runs independently. Account email needs an SMTP sender; push MFA uses a paired authenticator. |
| [KyPost](https://github.com/Busnes-app/KyPost-Server#readme) | Webmail, SMTP sending, folders, contacts, scheduled mail and OpenPGP, with optional local AI sorting. | Use an existing IMAP/SMTP mailbox. Native mailbox receiving is still in qualification; KyIdentity is optional. |
| [KyNotes](https://github.com/Busnes-app/KyNotes-server#readme) | Browser-encrypted text and ink notebooks, attachments, tasks and team sharing. | Local administrator/everyday accounts or optional KyIdentity. Complete recovery needs the capsule and a separate encrypted-blob backup. |
| [KyCalendar](https://github.com/Busnes-app/KyCalendar#readme) | Personal and group calendars in the browser and CalDAV clients, with per-device app passwords. | Local accounts/groups work independently; KyIdentity is optional. AI agents connect over MCP with revocable tokens. Invitations through KyPost are not finished yet. |
| [KyDrive](https://github.com/Busnes-app/kydrive-server#readme) | Permissioned workspaces, file/folder sharing, versions, trash, filename search and WebDAV; optional document editing and desktop sync. | Staff are provisioned through KyIdentity. Euro-Office is a separate optional editor. Recovery needs matching metadata and bulk snapshots. |
| [KyMessages](https://github.com/Busnes-app/KyMessage-Server#readme) | A Matrix operator console and team chat stack, with encrypted rooms and optional calls. | The base image is a console. Chat needs Synapse, MAS, PostgreSQL, Element, KyIdentity and HTTPS; calls need the media setup. Evaluation and acceptance gates remain explicit. |
| [KyRecovery](https://github.com/Busnes-app/KyRecovery-server#readme) | A blind store for sealed capsules, integrity/audit records, replication and restore planning. | Local operator sign-in or optional KyIdentity. Custodians hold the recovery shares; products restore outside the store. A capsule count is not a restore test. |
| [KyYard](https://github.com/Busnes-app/KyYard-server#readme) | Docker/Kubernetes fleet inventory, container controls, logs, images and remote-agent enrollment. | Local accounts and MFA work independently. The default Docker socket mount grants host-level authority; suite management needs a runner handoff. |
| [KyDNS](https://github.com/Busnes-app/KyDNS-server#readme) | Private DNS/service names, filtering, per-network views and replication; DHCP on supported installation paths. | Runs independently. Verify UDP/TCP DNS before switching clients; LAN-attached Compose does not support DHCP. |
| [kyPulse](https://github.com/Busnes-app/KyPulse-server#readme) | Read-only health polling, log collection, audit activity and webhook alerts. | Local sign-in works independently. Add health sources and an alert receiver; KyYard adds container facts/logs. Monitoring reports problems; it does not repair them. |

## Native clients and authenticators

- **KyPost:** [Android](https://github.com/Busnes-app/KyPost-for-Android#readme),
  [macOS and iOS](https://github.com/Busnes-app/KyPost-for-Mac#readme),
  [Linux desktop and Plasma Mobile](https://github.com/Busnes-app/KyPost-for-Linux#readme).
  Pair with a KyPost server; they do not connect directly to IMAP/SMTP. Packages, signing,
  source builds and device requirements differ by platform.
- **KyAuth:** [Android](https://github.com/Busnes-app/KyAuth-android#readme),
  [iPhone/iPad](https://github.com/Busnes-app/KyAuth-iOS#readme),
  [Linux phones](https://github.com/Busnes-app/KyAuth-Linux#readme).
  Generate local TOTP codes or pair KyIdentity for push MFA. Supported app sign-on varies
  by platform. TOTP entries have no backup, export or sync; keep each site's recovery codes.
- **[KyDrive desktop](https://github.com/Busnes-app/kydrive-desktop#readme):** Windows,
  macOS and Linux workspace sync, in development. Requires an M7-compatible KyDrive server
  and browser approval of the linked computer. Synchronization is separate from backup.

## Installation tools

- **[KyQuickStart](https://github.com/Busnes-app/KyQuickStart#readme):** pre-release
  command-line installer for its supported catalog on prepared Docker/SSH or Kubernetes
  targets. It does not install Docker or Kubernetes; release and runner limits are documented.
- **[KyQuickStart AI](https://github.com/Busnes-app/KyQuickStart-AI#readme):** guides a local
  coding agent through selected installations and produces a handover and findings report.
  The report must distinguish completed, failed and blocked checks; an agent run is not a
  guarantee of working integrations or complete recovery.
- **[ky-kubernetes](https://github.com/Busnes-app/ky-kubernetes#readme):** site-specific
  deployment and migration reference, rather than a portable apply-everything installer.

## Readiness and recovery

Capabilities describe the current source; published images and client packages may be at
different revisions. Check each repository's release and test documentation. Unit tests,
local fixtures and example screenshots do not establish live provider delivery,
physical-device behavior or production readiness.

KyRecovery cannot open your backups. A complete restore may also need encrypted blobs,
file snapshots, deployment keys and users' own recovery material. Verify the product's
whole restore procedure with the real custodian cards before relying on it.

## Shared code

[ky-primitives](https://github.com/Busnes-app/ky-primitives) provides shared Go security and
recovery components; [ky-server-base](https://github.com/Busnes-app/ky-server-base) is a
server scaffold; [ky-ui](https://github.com/Busnes-app/ky-ui) supplies the shared web theme.

## Help and contributing

Ask setup questions, share what you run and suggest ideas in
[Discussions](https://github.com/Busnes-app/.github/discussions). Open an issue on the relevant
product repository for bugs. Report
security problems privately through the [security policy](https://github.com/Busnes-app/.github/blob/main/SECURITY.md).
For Busnes.app project enquiries, write to hello@busnes.app.
