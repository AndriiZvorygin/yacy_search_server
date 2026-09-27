# Repository Instructions

## Committing And Pushing Significant Changes

After completing and validating a significant code change, commit the
task-related changes and push the commit to the current working branch. Do not
leave substantial completed implementation work only in the local working tree
without clearly telling the user why it remains uncommitted or unpushed.

- Before committing, inspect the working tree and stage only files belonging
  to the task; preserve unrelated or pre-existing user changes.
- Run the relevant focused tests and checks before committing, and report any
  validation that could not be completed.
- Push to the branch's configured remote after the commit succeeds. If the
  remote is unavailable, the branch has diverged, or pushing would include
  unrelated work, stop and explain the specific issue rather than force-push.
- Respect an explicit user instruction not to commit or push, and do not
  include secrets, generated artifacts, or unreviewed changes.

## Web UI, API, Help, And Localization

When changing YaCy web pages or API endpoints, update all matching user-facing and tool-facing artifacts in the same change.

- For `htroot/**/*.html` changes, update the corresponding localization files under `locales/` when visible text, labels, form controls, messages, or navigation text changes.
- For `htroot/**/*.html` changes, update the corresponding Markdown help file under `help/`.
- For API or servlet behavior changes under `source/net/yacy/htroot/**`, update the related `help/**/*.md` file with changed endpoints, access requirements, parameters, side effects, response fields, and automation guidance.
- Treat `locales` and `help` updates as required checklist items for HTML, servlet, and API changes. Do not leave them for a follow-up unless the change is explicitly internal and has no user-visible page, request parameter, response, or behavior impact.

## Tests During Code Reviews

Do not treat the repository-wide test backlog as a separate mass-rewrite project unless explicitly requested. Improve tests incrementally in the context of individual code reviews.

- During each code review, identify the behavior affected by the reviewed code and add, update, or repair focused tests where they provide useful regression coverage.
- Keep test work scoped to the reviewed area and the changes needed to verify it.
- Report unrelated existing test failures, but do not expand the review into a repository-wide test cleanup solely because those failures exist.
- Over time, use successive reviews to bring the test suite up to date alongside the production code.
