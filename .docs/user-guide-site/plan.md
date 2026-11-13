# Plan

1. Replace the starter: branding (amber palette, logo, favicon), navigation for 25 pages (User guide + Developer guide tabs), screenshots under images/.
2. CI: `.github/workflows/docs.yml` — validate + broken links on PRs and main; deploy job on main via the Mintlify API (secrets MINTLIFY_API_KEY, MINTLIFY_PROJECT_ID; skipped when absent).
3. Write the pages (4 writers in parallel, one per section group), then the developer guide after the plugin API fix lands in the app repo.
4. Validate locally, prune unreferenced images, open the PR, merge after CI, ask the owner for the two secrets.
