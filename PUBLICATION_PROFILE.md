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

The previous journal URL under `https://fiverocksgames.github.io/games/math-defender/journals/` remains a compatibility entry point during migration. Historical journal screenshots continue to be served from the existing `/games/math-defender/assets/journals/` paths so old links and articles do not break.
