# Math Defender public journal publication profile

This repository is the canonical public deployment repository for Math Defender under the namespace model in `fiverocksgames/devops-standards`.

- Private development: `fiverocks-dev/math-defender`
- Public deployment: `fiverocksgames/math-defender`
- Pages URL: `https://fiverocksgames.github.io/math-defender/`
- Journal URL: `https://fiverocksgames.github.io/math-defender/journals/`
- English journal URL: `https://fiverocksgames.github.io/math-defender/en/journals/`
- Branch: `main`
- Formal directory: repository root
- Prerelease directory: not adopted for the journal site
- Credentials: GitHub Pages deployment uses repository-scoped `GITHUB_TOKEN` permissions only

## Journal exception

The public journal is intentionally authored as public Markdown/Jekyll content and rendered by the GitHub Pages publication workflow. This is not a build of the private Unity game and does not include private game source, tests, worklogs, internal design documents, source maps, credentials, or runner responsibilities.

The WebGL game build remains outside this journal migration and continues to follow the private-source/public-output separation defined by the shared Public Web Game Deployment Policy.

## Migration compatibility

The previous journal URL under `https://fiverocksgames.github.io/games/math-defender/journals/` remains a compatibility surface for existing links while new journal authoring and discovery use this repository's canonical journal URLs.

Historical journal screenshots continue to be served from the existing `/games/math-defender/assets/journals/` paths so old links and migrated articles do not break. These assets MUST NOT be removed or relocated without separate migration evidence that verifies the historical URLs continue to resolve.

The legacy company-site collection, layouts, configuration, and individual journal entry routes may remain while compatibility is required. They SHOULD NOT receive new journal entries after the canonical authoring cutover. Any later removal MUST be backed by explicit evidence that all dependent routes have a verified replacement or redirect.

## Activation status

GitHub Pages activation is verified.

- Migration source commit: `bb3bb1d31e948f613467dbd737f742c02955faf7`
- Pages workflow run: `33389466553`
- Verified attempt: `2`
- Result: `success`

The `Deploy Math Defender Journal Pages` workflow is adopted for automatic journal publication on `push` to `main`. `workflow_dispatch` remains available for manual recovery or republication.

This automatic trigger applies only to the intentionally public Markdown/Jekyll journal site in this repository. It does not adopt automatic Unity/WebGL prerelease or formal game deployment.

The canonical Korean and English journal entry points are:

- `https://fiverocksgames.github.io/math-defender/journals/`
- `https://fiverocksgames.github.io/math-defender/en/journals/`

Company-site integration is handled as a compatibility/consumer concern. The company homepage may link directly to these canonical URLs while preserving existing `/games/math-defender/journals/**` routes and historical screenshot assets until their compatibility obligations are independently retired with evidence.
