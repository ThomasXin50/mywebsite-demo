# Demo portfolio — content repo

This repository holds the **sample content** behind the public demo of my portfolio's admin
editor, at **https://demo.thomasxin.me**. Anyone can open it and edit, with no sign-in. Every Save
there is a real commit to this repo, made through the same pipeline my real admin uses:

1. the latest version of the file is read from `main`,
2. your change is applied and the whole site's content is validated (schemas and cross-file
   checks; anything invalid is refused with the reason, and nothing is committed),
3. the change is committed here as one commit, with the readable `index.preview.md` copy
   regenerated beside it.

The "Commit" link that appears after you save opens that commit here.

**Everything here is placeholder content** ("Demo project 1", "Demo award (placeholder)"). Every
night the repo is reset to the original seed, **history included**, so anything typed in the demo
is gone the next morning.

The real site is **https://www.thomasxin.me**.

## How the demo differs from the real admin

The demo is the same build of the admin with one setting switched on. What's different:

| | Real admin (admin.thomasxin.me) | Demo (demo.thomasxin.me) |
|---|---|---|
| Who can edit | Only me, via GitHub sign-in | Anyone, no sign-in |
| Where saves go | My site's repo; the live site redeploys in about a minute | This repo; there's no live site, the commit is the result |
| "View live page" link | Opens the page on www.thomasxin.me | Not shown; "Real site" links to my portfolio instead |
| Large files (videos, files over 3 MB) | Uploaded straight to Cloudflare R2 storage | Turned off: refused with a message, and the Media page says storage isn't set up |
| Video blocks | Supported | Supported, but the sample content has none (only small files can be added) |
| Save limit | None | About 40 saves per visitor per 10 minutes |
| Lifetime of edits | Permanent | Until the nightly reset |
| Content | My real projects, achievements, and résumé | Blank sample entries that between them use every feature |

Everything else is the same: in-place editing of fields, the Markdown body editor with a live
preview, new and deleted entries, image uploads (resized in the browser), covers (extend or crop),
the Files section, tags/stack/kind management with merges, the home page and settings editors,
block reordering and pebble-frame rerolls (Arrange), and the click-to-play demo block.

## Layout

`content/` mirrors the real site's content folder: `site.json` (name, links, taxonomies),
`home/`, `projects/<slug>/`, `achievements/<slug>/`, and `resume/`, each with an `index.json` and
its images and files. `*.preview.md` files are generated readable copies; don't edit them.
