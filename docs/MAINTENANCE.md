# Maintenance Checklist

This checklist is for safe cleanup and performance improvements that should not change website behavior.

## Before Changes

1. Confirm active pages (`index.html` is primary).
2. Identify exact runtime files loaded by `<link>` and `<script>`.
3. Avoid deleting anything that is still referenced.

## Dependency Hygiene

1. Keep `package.json` dependencies limited to what build/dev actually needs.
2. Keep `package-lock.json` in sync after dependency changes.
3. Keep `node_modules/` out of git.

## Vendor Hygiene

1. Keep only the minified files used at runtime in `vendor/`.
2. Exclude source maps and unminified variants unless required for debugging.
3. Regenerate vendor assets with `npm run vendor` after version updates.

## Content and Markup Hygiene

1. Use a single charset declaration (`utf-8`).
2. Keep image dimensions explicit where possible to reduce layout shift.
3. Prefer meaningful `alt` text for accessibility.

## Validation Pass

Run these checks before commit:

```bash
git status --short
rg -n "vendor/" index.html old_news.html
rg -n "charset" index.html old_news.html
```

Optional local runtime check:

```bash
npm run dev
```
