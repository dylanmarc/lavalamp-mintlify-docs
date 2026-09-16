# FlatApp documentation

Mintlify documentation site for [FlatApp](https://github.com/dylanmarc/flatapp-v2), a PWA for shared households.

## Two sections

| Tab | Path | Audience |
| --- | --- | --- |
| **Internal** | `index.mdx`, `internal/` | Engineering. Architecture, schema, RPCs, Edge Functions, environments, runbooks. |
| **User guide** | `user-guide/` | Customers. Written to be published as-is when the site goes public. |

## Privacy

**This site is private.** Two mechanisms, both should stay on until you decide otherwise:

1. `noindex: true` in every page's frontmatter, so crawlers do not index them.
2. Access control on the Mintlify deployment, which is what actually prevents access.

`noindex` is a request to crawlers, not a lock. Configure access control in the Mintlify dashboard.

See `internal/contributing/documentation.mdx` for the checklist to follow when publishing the user guide.

## Local preview

```bash
npm i -g mint
mint dev          # http://localhost:3000
```

Run from the repo root, where `docs.json` lives.

## Structure

```
docs.json                  Site config: theme, colours, navigation tabs
index.mdx                  Internal landing page
internal/
  architecture.mdx         System overview
  tech-stack.mdx
  repo-structure.mdx
  data-model.mdx           Every table
  security-rls.mdx         RLS and SECURITY DEFINER rules
  database-functions.mdx   RPC reference
  edge-functions.mdx       The ten Edge Functions
  notifications-pipeline.mdx
  scheduled-jobs.mdx
  frontend-architecture.mdx
  data-fetching.mdx        Query keys and optimistic mutations
  realtime.mdx
  conventions.mdx
  features/                Per-feature deep dives
  ops/                     Environments, local dev, deployment, migrations, runbook, observability
  contributing/            Workflow, adding a feature, maintaining these docs
user-guide/
  introduction.mdx ... polls.mdx
  rewards/
  account/
logo/, favicon.svg
```

## Adding a page

1. Create the `.mdx` file with `title`, `description`, and `noindex: true` in the frontmatter.
2. Add its path to the right group in `docs.json`. A file not listed in the navigation does not appear on the site.

## Publishing changes

Install the Mintlify GitHub app from the [dashboard](https://dashboard.mintlify.com/settings/organization/github-app). Pushes to the default branch deploy automatically.
