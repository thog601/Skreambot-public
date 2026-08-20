# Team Guides — format spec

These files are the source for the `/team-guide` command. The bot fetches the
raw `.md` from jsDelivr, reads the frontmatter for the footer, and splits on
`## ` headers to build the section select-menu.

Keep the format consistent or the parser will miss sections.

## File naming
- One file per team, named with the canonical team slug: `admech.md`,
  `lavistodes.md`, `battlesuit.md`, `neurothrope.md`, `multi_hit.md`,
  `rapid_assault.md`.
- Lowercase, underscores (matches the `teams` reference tab). No apostrophes,
  no spaces.

## Frontmatter (required)
A YAML block at the very top, between `---` fences:

```
---
team: admech
display: Adeptus Mechanicus
updated: 2026-08-17
meta_status: "Pre-[patch] meta — verify before a serious push"
---
```

- `team` — the slug (must match the filename).
- `display` — human-readable name shown in the embed title.
- `updated` — ISO date, surfaced in the footer so readers know how stale it is.
- `meta_status` — free text for the footer. Start it with `DRAFT` while the
  guide is unfinished; the bot should skip / not list DRAFT guides.

## Sections (fixed set, fixed order)
Use these exact `## ` headers. Omit any that don't apply — a missing header just
means that option won't appear in the menu.

- `## Overview` — comp list, one-line TL;DR, when to run this team. This is the
  default landing view, so keep it tight.
- `## Core Mechanics`
- `## Turn-by-Turn`
- `## Flex Options` — subs, placeholders for weaker rosters, situational swaps.
- `## Tips & Edge Cases`
- `## Summary` — checklist or TL;DR.

## Style notes
- Discord embed descriptions cap at ~4096 chars, and the bot paginates per
  section, so keep any single section comfortably under that.
- Write for someone who does NOT already run the team — spell out unit names on
  first use rather than relying on nicknames.
