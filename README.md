# ijbema.com

A static Jekyll site for a solo software consultant helping engineering teams improve their development processes, including AI tooling adoption.

## Run locally

Requirements:

- Ruby with Bundler
- The gems listed in `Gemfile`

Install dependencies and start the development server:

```sh
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) to preview the site. To serve it with an empty base URL, use:

```sh
bundle exec jekyll serve --baseurl=""
```

## Publish with GitHub Pages

This project uses Jekyll's native build and does not require a GitHub Actions workflow. Push the repository to GitHub, then enable GitHub Pages for the repository and select the branch that contains the site source. GitHub Pages will build the site from `_config.yml` and the files in this repository.

Before publishing, replace the `[PLACEHOLDER: ...]` content and update the site settings in `_config.yml`, including the title, description, email address, LinkedIn URL, and repository name.
