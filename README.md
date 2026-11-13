# YourSSH documentation

Source of the YourSSH documentation site, built with [Mintlify](https://mintlify.com). The app lives in [YoursshLabs/yourssh](https://github.com/YoursshLabs/yourssh).

## Preview locally

```bash
npx mint dev            # http://localhost:3000
npx mint validate       # the same build check CI runs
npx mint broken-links
```

Requires Node.js 20.17 or newer.

## Structure

- `docs.json` — site config and navigation. A page must be listed here to be published.
- `index.mdx`, `installation.mdx`, `quickstart.mdx` — getting started.
- `user-guide/` — one page per feature.
- `developer-guide/` — building from source, architecture and plugins.
- `images/<NN-section>/` — screenshots from the app repo's isolated docs journey (`tool/docs_journey.sh`), resized to at most 1440 px wide.

Writing rules and terminology: [AGENTS.md](AGENTS.md).

## Build and deploy

`.github/workflows/docs.yml`:

- Every pull request and every push to `main` run `mint validate` and `mint broken-links`.
- After those pass on `main`, the workflow asks Mintlify to deploy the site and waits for the result. It uses the repository secrets `MINTLIFY_API_KEY` (an admin API key, `mint_…`) and `MINTLIFY_PROJECT_ID`, both from the Mintlify dashboard's API keys page. Without them the deploy step is skipped with a warning.

To make CI the only way the site deploys, turn off automatic deployments for this repository in the Mintlify dashboard after adding the secrets.
