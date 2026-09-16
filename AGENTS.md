# Documentation project instructions

## About this project

- Mintlify documentation site for **FlatApp**, a PWA for shared households
- The app it documents lives at [`dylanmarc/flatapp-v2`](https://github.com/dylanmarc/flatapp-v2)
- Pages are MDX with YAML frontmatter; configuration is `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Two audiences, two voices

This site has two tabs and they are written differently.

**`internal/` and `index.mdx`** - for an engineer with access to the app repository. Name files, tables, functions, and migrations. Explain *why* something is the way it is, especially where the code looks wrong but is not. Say plainly where something is stale, missing, or a known wart.

**`user-guide/`** - for someone on a phone trying to split a bill. Never mention tables, RPCs, Supabase, migrations, or repository paths. Never link to the app repository. These pages are written to be published as-is.

## Privacy

Every page carries `noindex: true`. Keep it there. The user guide's copy is public-ready, but the site is not published yet - see `internal/contributing/documentation.mdx` for the checklist before removing `noindex` from anything.

## Terminology

- **Flat**, not "household", "group", or "apartment"
- **Flatmate**, not "roommate" or "user", in user-facing copy
- **Member** is fine internally, where it maps to a `flat_members` row
- **Chore** repeats and rotates; a **todo** happens once; a **reminder** is a date
- **Rota** and **rotation** both work; prefer "rota" in user-facing copy

## Style preferences

- Active voice and second person ("you")
- One idea per sentence
- Sentence case for headings
- Bold for UI elements: click **Settings**
- Code formatting for file names, commands, paths, and code references
- No em dashes; use normal hyphens

## Content boundaries

- Never put real credentials, keys, project refs, or customer data in a page
- Never document a feature that is not shipped; if something is scaffolded but inert, say so explicitly (see `internal/features/billing.mdx`)
- Do not duplicate the app repo's `docs/` folder - migrate content here and delete the original
- Where a page and the code disagree, the code is right and the page is a bug

## Accuracy

Values that exist in both SQL and TypeScript (XP, coins, prices, drop rates, level thresholds) are documented with the numbers from the source. Check the migration or constants file before changing one in a page.
