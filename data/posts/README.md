# Blog post workflow

To publish a new article:

1. Copy `data/posts/_template.json`.
2. Rename it to a new slug, for example: `my-new-article.json`.
3. Fill the fields (`id`, `title`, `description`, `tags`, `lang`, `content`).
4. Leave `publishedAt` empty to use the file first-commit date/time automatically,
   or set it manually in ISO format (`2026-02-16T18:30:00Z`).
5. Commit and push.

GitHub Actions runs `scripts/build-posts-index.js`, regenerates `data/posts.json`,
and sorts posts from newest to oldest by `publishedAt`.

Notes:
- `id` must be unique.
- `tags` must be a non-empty array of strings.
- Use double line breaks in `content` to split paragraphs in the post page.
