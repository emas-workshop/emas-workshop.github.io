# EMAS main page

A single-page version of the EMAS workshop series website, built with the actual **So Simple 3.2.0 Jekyll theme**. Includes the workshop history, 14 editions (2013–2026), current and former steering committee, publication links, and community resources. Individual workshop websites remain external links.

Original website code is licensed under the MIT License. The So Simple theme and other third-party components retain their respective licences and copyright notices. Website content and the EMAS logo are excluded from the code licence unless otherwise stated.

## Edit the page

The wiki has more details but in general this is the structure:

| File | Content |
| --- | --- |
| `index.html` | Main-page text and section order |
| `_data/workshops.json` | Annual editions and bibliographic records, newest first |
| `_data/committee.json` | Current and former members, websites, and email addresses |
| `_data/resources.json` | Research resources, organised by category |
| `_data/navigation.json` | Navigation labels and anchors |
| `_includes/masthead.html` | Header and latest-edition summary |
| `_config.yml` | Site title, metadata, and Jekyll settings |
| `assets/css/workshop.css` | Visual customisations layered over So Simple |

When adding a new edition, put it first in the workshop data and include its `dates` and `location`; the latest-edition summary updates automatically. Earlier editions, former members, and resources expand in place. Their original anchor IDs are preserved, including `#s-c`, `#work`, and year anchors such as `#2020`. Email links use valid `@` addresses.

## Local development

Install Ruby 3.3 and Bundler, then run:

```sh
gem install bundler -v 2.5.22
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --livereload
```

Open http://localhost:4000. For a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

The generated site is in `_site`. GitHub Actions builds from the Jekyll source.

See `THEME.md`, `LICENSE.md` and `LICENSE-theme.txt` for provenance and licensing.
