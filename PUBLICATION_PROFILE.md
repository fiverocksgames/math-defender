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

## Journal authoring source

New public Math Defender journal entries are authored in this repository under:

`_math_defender_journals/`

The legacy collection at `fiverocksgames/fiverocksgames.github.io/_math_defender_journals/` is retained only for compatibility/history during the website cutover and is not the authoring source for new entries.

Korean and English entries should remain paired through their `permalink` and `translation_url` front matter. The standalone site publishes Korean entries under `/journals/` and English entries under `/en/journals/`.

## Journal exception

The public journal is intentionally authored as public Markdown/Jekyll content and rendered by the GitHub Pages publication workflow. This is not a build of the private Unity game and does not include private game source, tests, worklogs, internal design documents, source maps, credentials, or runner responsibilities.

The WebGL game build remains outside this journal migration and continues to follow the private-source/public-output separation defined by the shared Public Web Game Deployment Policy.

## Migration compatibility

Historical journal screenshots continue to be served from the existing `/games/math-defender/assets/journals/` paths so old links and migrated articles do not break.

Legacy journal pages and supporting code in `fiverocksgames/fiverocksgames.github.io` must not be removed merely because the standalone deployment is active. Redirect/cutover work must preserve compatibility for existing article URLs, internal links, and historical image assets. The screenshot assets remain outside the journal-source cutover and should continue to be served until a separate binary-asset migration is completed and verified.

## Activation status

The standalone GitHub Pages deployment is active.

Workflow run `33389466553` (`Deploy Math Defender Journal Pages`) succeeded on run attempt 2 for head SHA:

`bb3bb1d31e948f613467dbd737f742c02955faf7`

The successful attempt completed both the Jekyll build and GitHub Pages deployment jobs, including `Configure Pages`, `Build with Jekyll`, `Upload Pages artifact`, and `Deploy to GitHub Pages`.

The workflow is currently `workflow_dispatch`-only. Changing that trigger policy is a separate DevOps decision and is not implied by journal activation.

The canonical standalone publication URLs are:

- `https://fiverocksgames.github.io/math-defender/`
- `https://fiverocksgames.github.io/math-defender/journals/`
- `https://fiverocksgames.github.io/math-defender/en/journals/`

Legacy website cutover or redirects are managed separately in `fiverocksgames/fiverocksgames.github.io` and must preserve existing URLs and assets until independently verified.
