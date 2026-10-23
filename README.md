# Data Flow Control website

This repository publishes https://dataflowcontrol.github.io/.

The website source lives in [`docs/` in dataflowcontrol/data-flow-control](https://github.com/dataflowcontrol/data-flow-control/tree/main/docs).
Edit documentation there. Its `Publish documentation` workflow synchronizes
the files into this repository's `docs/` directory on pushes to `main`.
Changes made directly to this directory will be overwritten by the next sync.

## GitHub configuration

1. Push this initial checkout to the `main` branch.
2. In **Settings → Pages**, select **Deploy from a branch**, branch `main`,
   folder `/docs`, and save. Leave the custom domain blank.
3. Confirm https://dataflowcontrol.github.io/ loads before switching the original
   repository to redirect-only publishing.

The source repository needs an Actions secret named `WEBSITE_PUBLISH_TOKEN`.
Use a fine-grained personal access token with resource owner `dataflowcontrol`,
access only to this repository, and **Contents: Read and write** permission.
The organization may require approval of the token. Allow its owner to push to
`main` under any applicable branch rules. Renew the secret before token expiry.

Use a personal access token rather than the source repository's `GITHUB_TOKEN`:
the latter cannot write here, and pushes using `GITHUB_TOKEN` do not trigger
branch-based Pages builds.

See `developer-docs/website-publishing.md` in the source repository for the full
migration and verification steps.
