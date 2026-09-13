# yushang1994.github.io/yushangw

Personal academic website of Yushang Wei, built with [Jekyll](https://jekyllrb.com) on the
[AcademicPages](https://github.com/academicpages/academicpages.github.io) theme (a fork of
Minimal Mistakes) and hosted on GitHub Pages.

## Editing content

| What | Where |
| --- | --- |
| Home / about text | `_pages/about.md` |
| Research | `_pages/research.md` (PDFs in `files/pdf/research/`) |
| Teaching | `_pages/teaching.md` (syllabi in `files/pdf/teaching-materials/`) |
| Course materials | `_pages/teaching-materials.md` |
| CV | `_pages/cv.md` (PDF in `files/pdf/`) |
| Cake & Cat | `_pages/other.md` (photos in `images/baking/`, `images/aboutme/`) |
| Navigation menu | `_data/navigation.yml` |
| Name, bio, email, social links, avatar | `_config.yml` (`author:` section) |

Use `{{ site.baseurl }}/...` for links to files and images so they work both on
GitHub Pages (`/yushangw/...`) and if the site moves to its own domain.

## Running locally

```
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Then open <http://localhost:4000/yushangw/>.

## Deploying

Push to `main`; GitHub Pages rebuilds the site automatically (check the
"Actions" tab if a change doesn't appear after a minute or two).
