# Documentation Sanitization & Security Guidelines (`SECURITY.md`)

**Target:** Sanitized public documentation repository (`deshifrator-docs-public`) for the **Deshifrator** desktop application (`HTML`, `CSS`, `Markdown`, and `sources/DbStationary.Data`).

When reviewing Pull Requests, strictly enforce sanitization and confidentiality boundaries:

## 1. Public Sanitization & Confidentiality Rules
- **No Proprietary or Restricted Artifacts:** Ensure no confidential internal specifications, proprietary binary protocols not approved for public release, internal network topologies, or restricted organizational identifiers are introduced.
- **No Secrets, Credentials, or Real Paths:** Flag any database connection strings, passwords, API keys, certificates, internal server hostnames/IPs, or local developer file paths (`C:\Users\...`) in `sources/DbStationary.Data`, HTML files, or Markdown docs.
- **Anonymized Data Examples:** Verify that all sample records, identifiers, and exchange payloads in `data-exchange-and-mrz.html` and `docs/` use strictly synthetic/anonymized data.

## 2. Static Site & GitHub Actions Security
- **Safe HTML & External Links:** Ensure HTML pages do not load untrusted third-party scripts or external trackers, and that external links use `rel="noopener noreferrer"` where `target="_blank"` is present.
- **Workflow Least Privilege (`.github/workflows`):** Verify that GitHub Pages deployment workflows use minimal permissions (`permissions: contents: read`, `pages: write`) and pinned action versions.

## 3. Reporting Security or Sanitization Issues
- If you identify any un-sanitized internal information, credentials, or security issues in this repository, please notify the maintainer (`@ekatmoz88-alt`) privately before opening a public issue.
