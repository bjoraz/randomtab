# randomtab

A random-page new tab for the browser. Each time it opens, it sends you to a random site from a short list, including a random Wikipedia article chosen from a section of a Vital articles page.

Live at: https://bjoraz.github.io/randomtab/

## Files

| File | What it does |
|---|---|
| `index.html` | The new tab page. Picks one destination at random and redirects. |
| `vital.html` | Redirects to a random article from a section of a Wikipedia page (e.g. Vital articles). Pure JavaScript, works on GitHub Pages. |
| `index.php` | The original Random In Category tool (PHP), kept unchanged from upstream. It does not run on GitHub Pages. |

## Using `vital.html`

Default (Level 4 Physical sciences, Physics section):

```
https://bjoraz.github.io/randomtab/vital.html
```

Parameters, all optional:

| Parameter | Meaning | Default |
|---|---|---|
| `page` | Page to read links from | `Wikipedia:Vital_articles/Level_4/Physical_sciences` |
| `section` | Section name or number; leave empty (`section=`) for the whole page | `Physics` |
| `site` | Wikimedia host | `en.wikipedia.org` |
| `debug` | If set, shows how many articles were found and the chosen URL instead of redirecting | off |
| `purge` | If set, ignores the cached article list | off |

Examples:

```
vital.html?section=Astronomy
vital.html?page=Wikipedia:Vital_articles/Level_4/Biological_and_health_sciences&section=Biology
vital.html?section=Physics&debug=1
```

Notes:

- Sections are matched by name, so edits to the Vital articles page won't break the link. A section number also works.
- A section includes its subsections.
- Only existing articles are used (no red links, no project pages).
- The article list is cached in the browser's `localStorage` for one day.

## Changing the new tab destinations

Edit the `pages` array in `index.html`.

## Setting it as your new tab

Point your browser's new tab (or home page) at the live URL, using a new-tab extension if your browser needs one.

## Credits and license

Based on [randomincategory](https://gitlab.wikimedia.org/toolforge-repos/randomincategory) by [Ahecht](https://en.wikipedia.org/wiki/User:Ahecht), used under the MIT License. For documentation of the original PHP tool, see the [upstream repository](https://gitlab.wikimedia.org/toolforge-repos/randomincategory) or [randomincategory.toolforge.org](https://randomincategory.toolforge.org).

Released under the MIT License. See [LICENSE](LICENSE). The original copyright notice is retained as required.
