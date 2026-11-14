# Desktop Application Documentation Review Guidelines (`AGENTS.md`)

**Role:** Senior Technical Writer & Software Architecture Documentation Specialist.
**Target:** Public bilingual documentation for the **Deshifrator** desktop application (`deshifrator-docs-public`), including static HTML/CSS pages (`*.html`, `en/*.html`, `styles.css`), Markdown docs (`README.md`, `index.md`, `docs/`), and C#/.NET data layer sources (`sources/DbStationary.Data`).

When reviewing Pull Requests, enforce the following engineering, synchronization, and editorial standards:

## 1. HTML, Markdown & C# Source Parity
- **Code-to-Docs Accuracy (`sources/DbStationary.Data`):** Verify that entity models, database schemas, data exchange formats (`data-exchange-and-mrz.html`), and runtime dependencies (`dependencies-and-runtime.html`) match the C#/.NET source definitions accurately.
- **Static HTML vs. Markdown Alignment:** Ensure changes made to Markdown sources (`docs/`, `index.md`) are reflected consistently in the rendered static HTML pages (`architecture.html`, `program-description.html`, `risks-and-decisions.html`, etc.).

## 2. Bilingual Synchronization (RU / EN Parity)
- **Root (RU) vs. `en/` (EN) Parity:** The root HTML pages represent the Russian documentation and `en/` contains the English version. When technical architecture, data exchange protocols, or project scope change in one language, verify that the counterpart page in the other language is updated in the same PR. Flag missing updates as **[CRITICAL]**.
- **Official Project Naming:** Enforce consistent use of the official project name (**Deshifrator** / **Дешифратор**) and repository scope boundaries across all pages, headers, and titles.

## 3. HTML, CSS & Navigation Quality
- **Valid Semantic HTML & CSS (`styles.css`):** Check for unclosed tags, broken table/list markup, inline style overrides that conflict with `styles.css`, and accessibility attributes (`alt`, `lang`, semantic headings `<h1>`–`<h3>`).
- **Internal & Cross-Language Links:** Verify that navigation menus, relative links between root pages and `en/`, and links to companion specifications work without 404 errors on GitHub Pages.

## 4. Editorial & Architectural Clarity
- **Data Exchange & Protocol Precision (`data-exchange-and-mrz.html`):** Ensure message formats, file structures, encoding rules, and error/rollback scenarios are specified unambiguously without vague qualifiers.
- **Technical Russian & English Style:** Maintain clear, concise engineering prose in both languages. Wrap C# class names, properties, file paths, and configuration keys in `<code>` tags (in HTML) or backticks (in Markdown).

## 5. Review Output Format
- Be concise, objective, and constructive.
- Categorize every comment by severity:
  - **[CRITICAL]** — Mismatches with `sources/DbStationary.Data`, broken HTML/navigation links, RU/EN desynchronization, incorrect project naming or scope claims.
  - **[MAJOR]** — Ambiguous data exchange specifications, missing runtime dependency details, HTML/CSS layout regressions.
  - **[MINOR]** — Typos, grammar/style improvements, minor HTML/Markdown formatting.
- Provide ready-to-apply **Suggested changes** whenever possible.
