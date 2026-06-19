# AGENTS.md — fastapi-blog

Single-file FastAPI app (`main.py:7`) with Jinja2 templates and in-memory data. No database, no auth, no tests, no CI.

## Commands

| Action | Command |
|--------|---------|
| Dev server | `uv run fastapi dev main.py` |
| Production | `uv run fastapi run main.py` |
| Install deps | `uv sync` |
| Add dep | `uv add <package>` |

## Key conventions

- **Package manager**: `uv` (lockfile: `uv.lock`). Do not use pip/poetry.
- **Template engine**: Jinja2, `templates/` dir. Inheritance: `layout.html` → `home.html`.
- **Route naming**: HTML routes use `name="home"` / `name="posts"` for `url_for()` reverse lookups. Both hidden from OpenAPI schema (`include_in_schema=False`).
- **Static files**: mounted at `/static` in `main.py:9`. Referenced in templates via `{{ url_for('static', path='...') }}` (never hardcoded paths).
- **Data**: in-memory `posts: list[dict]` in `main.py:13`. No database yet.
- **No test/lint/typecheck tooling configured**.

## Gotchas

- `TemplateResponse` requires passing the `request` parameter: `templates.TemplateResponse(request, "template.html", {...})`.
- API endpoint (`/api/posts/{post_id}`) in `main.py:41` returns JSON; HTML routes return rendered templates.
