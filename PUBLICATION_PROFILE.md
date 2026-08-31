# Math Defender public journal publication profile

This repository is the canonical public deployment repository for Math Defender under the namespace model in `fiverocksgames/devops-standards`.

- Private development: `fiverocks-dev/math-defender`
- Public deployment: `fiverocksgames/math-defender`
- Pages URL: `https://fiverocksgames.github.io/math-defender/`
- Journal URL: `https://fiverocksgames.github.io/math-defender/journals/`
- Branch: `main`
- Formal directory: repository root
- Prerelease directory: not adopted for the journal site
- Credentials: GitHub Pages deployment uses repository-scoped `GITHUB_TOKEN` permissions only

## Journal exception

The public journal is intentionally authored as public Markdown/Jekyll content and rendered by the GitHub Pages publication workflow. This is not a build of the private Unity game and does not include private game source, tests, worklogs, internal design documents, source maps, credentials, or runner responsibilities.

The WebGL game build remains outside this journal migration and continues to follow the private-source/public-output separation defined by the shared Public Web Game Deployment Policy.

## Migration compatibility

The previous journal URL under `https://fiverocksgames.github.io/games/math-defender/journals/` remains the canonical compatibility entry point until the new Pages deployment is verified. Historical journal screenshots continue to be served from the existing `/games/math-defender/assets/journals/` paths so old links and articles do not break.

The old journal pages MUST NOT be removed or redirected until the new Pages deployment succeeds and the new Korean/English journal URLs, navigation, styles, and images have been verified.

## Activation status

Repository-side migration is prepared. Initial Pages workflow run `33389466553` failed at `actions/configure-pages@v5` because GitHub Pages is not yet enabled/configured for this repository with GitHub Actions as the source.

Automatic deployment on pushes is intentionally paused while this setting is unavailable. The workflow is `workflow_dispatch`-only until activation succeeds, preventing unrelated content commits from repeatedly producing known-failing deployment runs.

Required activation gate:

1. enable GitHub Pages for `fiverocksgames/math-defender` with source **GitHub Actions**;
2. run `Deploy Math Defender Journal Pages`;
3. verify the new site at `/math-defender/`, `/math-defender/journals/`, and `/math-defender/en/journals/` plus all article and image links;
4. only then replace legacy journal pages with redirects.

The legacy screenshot assets remain intentionally outside this cutover gate and should continue to be served until a separate binary-asset migration is completed and verified.
