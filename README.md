# WinRef — Windows Native & Active Directory Command Reference

A single-file, offline study reference for Windows and Active Directory commands.
Open `index.html` in any browser — no build step, no server, no dependencies.

**269 commands · 14 chapters · 3 tracks · 48 tools**

**Live:** <https://winref-command-reference.onrender.com>

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/Ramki479/winref-command-reference)

---

## Tracks

| Track | Chapters | Commands | What it covers |
| --- | --- | --- | --- |
| **Windows Native** | Command Prompt, PowerShell, WMI/CIM | 52 | Commands present on every Windows install — no RSAT required |
| **Native AD** | Active Directory | 14 | Domain, users, groups, policy and trusts via built-in CMD or RSAT |
| **AD Toolkit** | Tool Index, Situational Awareness, Enumeration & SMB, Kerberos Abuse, Credential Access, Execution & Lateral Movement, Poisoning/Relay/Coercion, Offline Cracking, Auditing & Reporting | 203 | PowerView, Rubeus, Impacket, Responder, Mimikatz, Hashcat and more |

Plus two quick-enumeration runbooks and a safety & scope page.

## Features

- **One-click copy** — click any command row and it lands on the clipboard.
- **Search** — <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>K</kbd> or <kbd>/</kbd> to focus. Searches command text, tool names, operating system and the tool index, with live hit counts.
- **Collapsible sidebar tracks** — the AD Toolkit group starts collapsed and expands when you search or scroll into it.
- **Per-row badges** — operating system, tool name, and requirement flags (`RSAT`, `GroupPolicy module`, `Elevated`).
- **Light / dark theme** — remembered in `localStorage`.
- **Print / PDF** — dedicated print stylesheet, ~29 pages.
- **Offline and self-contained** — one HTML file, no network requests, no tracking.

## Files

```
index.html                              the entire site (data, markup, styles, logic)
sources/
  Windows_Native_Commands.txt           raw source for the Windows Native track
  Windows_Native_AD_Command_Reference.txt  raw source for the Native AD track
  Tools of the Trade.txt                raw source for the AD Toolkit track
README.md
```

## Hosting on Render

The repo ships a `render.yaml` Blueprint, so Render needs no configuration.

**One-click:** open **<https://render.com/deploy?repo=https://github.com/Ramki479/winref-command-reference>**,
sign in with GitHub, approve the repo, and click **Apply**. The site is live at
`https://winref-command-reference.onrender.com` in about a minute.

**Or from the dashboard:** *New → Static Site → connect `winref-command-reference` →*

| Setting | Value |
| --- | --- |
| Branch | `main` |
| Build Command | *(leave empty)* |
| Publish Directory | `.` |

Afterwards, every push to `main` redeploys automatically. Static sites are free on Render, served
from a global CDN with HTTPS, and support a custom domain under *Settings → Custom Domains*.

## Editing

All content is data-driven. Inside `index.html`:

- `COMMANDS` — one object per command: `{tabs, section, cmd, purpose}` plus optional `tool`, `os`, `admin`, `rsat`, `gp`, `defender`.
- `TOOLS` — the 48-entry glossary rendered by the Tool Index chapter.
- `CHAPTERS` — chapter order, kickers, intros, tips and section keys.
- `TRACKS` — which chapters belong to which sidebar group.

Add a command to `COMMANDS` with a matching `section` key and it appears in the right place; counts update at runtime.

## Sanitisation

`Tools of the Trade.txt` was extracted from a training lab and originally contained lab passwords,
NTLM/NTLMv2 hashes, Kerberos tickets and NTDS dump lines. Before publication every credential was
replaced with a placeholder (`<password>`, `<hash>`, `<blob>`, `<challenge>`). Command syntax, hostnames
and principals are unchanged; no real secret from that material is reproduced here.

The site itself contains placeholders only — `<username>`, `<host>`, `<domain>`, `<password>`, `<hash>`.
Substitute your own values.

## Use

For study, and for systems you own or are explicitly authorised to assess. Nothing here is a licence to
test third-party infrastructure.

Source material and third-party tools belong to their respective authors. This is a personal
compilation of notes and syntax, provided as-is.
