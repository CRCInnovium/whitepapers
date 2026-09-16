# InnoviumAI Whitepapers

Official whitepapers and research publications from InnoviumAI.

Published at https://crcinnovium.github.io/whitepapers/ using GitHub Pages
from `main/docs`. Shared Jekyll layouts provide the library and publication pages.

## Adding publications

Create `docs/publications/YYYY/descriptive-slug/index.md` and place its PDF
alongside it. Copy the front matter from an existing publication, keeping
`layout: publication`, and update the title, authors, document date, description,
document type, and PDF path. Write the abstract below the front matter.
The home page lists publications automatically, newest first, grouped by year.
Optional fields include `cover`, `subtitle`, `topics`, `version`, and
`submission_note`; omit fields that do not apply.

Paths in `pdf` and `cover` start with `/` and exclude `/whitepapers`;
the templates add the configured site base path. Keep existing publication
folders and PDF filenames unchanged so that shared links continue to work.
For a later revision that needs a distinct citation, add a versioned PDF
filename and retain the previous file.

## Local preview

With Ruby and Bundler installed:

```sh
bundle install
bundle exec jekyll serve --source docs
```

Open http://localhost:4000/whitepapers/. Check the library, publication page,
and PDF links at both desktop and mobile widths before publishing.

## Copyright

© 2026 Technology Innovation Institute Abu Dhabi. All rights reserved.

No license is granted to reproduce, redistribute, or modify this work,
except as permitted by applicable law.

Bundled IBM Plex fonts retain their own licenses in `docs/assets/`.
