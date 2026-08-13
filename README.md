# CircleChatDemo®

Sample DITA Documentation Project — Oxygen XML Editor

## 📖 About This Project

**CircleChatDemo®** is a fictional team-messaging desktop application used as the subject of this sample DITA documentation project. The project is bundled with *Oxygen XML Editor* to demonstrate real-world DITA authoring patterns including conditional filtering, content reuse, key references, and multi-platform task authoring.

The application lets users create named *Talks* (persistent chat rooms), exchange direct messages, share files, react with emoji, and manage their account — all from a cross-platform desktop client available on Windows, macOS, and Linux.

## 📁 Project Folder Structure

```
circlechat/
├── circle-chat.ditamap        — root DITA map (TOC + key definitions)
├── README.md                 — this file
├── topics/                   — concept and reference topics
├── tasks/                    — procedural task topics
├── reusables/                — shared/conref content fragments
├── filters/                  — DITAVAL conditional filtering files
└── images/                   — screenshots and graphics
```

## ⚙️ DITA Features Demonstrated

### Conditional Filtering (DITAVAL)

Topics are tagged with the `audience` attribute and filtered at publish time using two DITAVAL profiles:

#### 🔧 administrator.ditaval

Includes administrator-only content (system requirements, installation, user management) and excludes end-user-only topics.

#### 👤 enduser.ditaval

Includes end-user-facing content (getting started, UI, keyboard shortcuts) and excludes administrator-only topics.

### Content Reuse (conref)

Shared content fragments live in the `reusables/` folder and are pulled into multiple topics via DITA `conref` attributes, avoiding duplication:

- `r_common_notes.dita` — product introduction paragraph, network port list, proxy note
- `r_installation.dita` — common installation prerequisites reused across all three platform-specific installation tasks

### Key References (keyref)

The DITA map defines the following keys, allowing topic content to reference them symbolically rather than hard-coding values:

- **product** — Resolves to the product name **CircleChatDemo®**. Used throughout topics via `<keyword keyref="product"/>`.
- **download_site** — External link to `http://sample.circlechat.com` — the product download page.
- **account_portal** — External link to `http://sample.circlechat.com/account` — the account management portal.

### Topic Types

- **Concept** — background and explanatory content (Getting Started, UI overview, Installation overview)
- **Task** — step-by-step procedures (platform-specific installation, account management)
- **Reference** — look-up information (system requirements, keyboard shortcuts, release notes, glossary)
