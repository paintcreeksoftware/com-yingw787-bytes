# Bytes by Ying

Personal blog by [Ying Wang](https://yingw787.com/) on technical deep dives and bugfixes. Built with AstroPaper v5 on Astro.

Live at: **[bytes.yingw787.com](https://bytes.yingw787.com)**

## Project Structure

```text
/
├── public/
│   ├── pagefind/         # auto-generated at build time
│   └── favicon.svg
├── src/
│   ├── assets/
│   │   ├── icons/
│   │   └── images/
│   ├── components/
│   ├── data/
│   │   └── blog/
│   │       └── YYYY/MM/DD/slug.md
│   ├── layouts/
│   ├── pages/
│   ├── scripts/
│   ├── styles/
│   ├── utils/
│   ├── config.ts
│   ├── constants.ts
│   └── content.config.ts
└── astro.config.ts
```

Blog posts live in `src/data/blog/YYYY/MM/DD/slug.md` and are served at `/posts/YYYY/MM/DD/slug`.

## Adding a Post

Create a markdown file at the right path:

```text
src/data/blog/2025/06/15/my-post.md
```

Minimum frontmatter:

```yaml
---
title: My Post Title
pubDatetime: 2025-06-15T12:00:00Z
description: A short description.
draft: false
tags:
  - general
---
```

Notes:

- Use `T12:00:00Z` (noon UTC) to avoid off-by-one date display in negative UTC offset timezones
- Quote titles/descriptions that contain `#` or `: `
- Inline LaTeX: `$2^n$`, block LaTeX: `$$...$$`

## Tech Stack

- **Framework** — [Astro](https://astro.build/)
- **Styling** — [Tailwind CSS v4](https://tailwindcss.com/)
- **Search** — [Pagefind](https://pagefind.app/)
- **Syntax highlighting** — [Shiki](https://shiki.style/) (solarized-light / solarized-dark)
- **Math rendering** — [KaTeX](https://katex.org/) via remark-math + rehype-katex
- **Icons** — [Tabler Icons](https://tabler-icons.io/)
- **Font** — [Google Sans](https://fonts.google.com/specimen/Google+Sans)

## Commands

| Command            | Action                                    |
| :----------------- | :---------------------------------------- |
| `pnpm install`     | Install dependencies                      |
| `pnpm dev`         | Start dev server at `localhost:4321`      |
| `pnpm build`       | Build to `./dist/` + generate search index|
| `pnpm preview`     | Preview the production build locally      |
| `pnpm format`      | Format with Prettier                      |
| `pnpm lint`        | Lint with ESLint                          |

## Environment Variables (optional)

```bash
# .env
PUBLIC_GOOGLE_SITE_VERIFICATION=your-value  # Google Search Console
```

## License

MIT
