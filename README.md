# ACCoRD – A Community for Contract Regulation for Data

ACCoRD public repository for the GitHub pages.

⚠️ Please do not include any private or sensitive data here – this is a public-facing repository.

ACCoRD aims to address barriers in data access and contracting that delay or block research using the UK's federated Digital Research Infrastructure (DRI). Data contracts are often complex, bespoke, and inconsistent, causing delays of up to 9 months and making data sharing costly and inefficient.

For ACCoRD project management, a private repository, please go to: [accord_project_management](https://github.com/UCL-ARC/accord_project_management)

---

### Team

- Project Lead: Dr Michelle Harricharan, [m.harricharan@ucl.ac.uk](mailto:m.harricharan@ucl.ac.uk)
- Project Co-Lead: Dr Claire Ellul, [c.ellul@ucl.ac.uk](mailto:c.ellul@ucl.ac.uk)
- Project Co-Lead: Dr James Wilson, [j.a.j.wilson@ucl.ac.uk](mailto:j.a.j.wilson@ucl.ac.uk)
- Research & Innovation Associate: Katie Buntic, [k.buntic@ucl.ac.uk](mailto:k.buntic@ucl.ac.uk)
- Research & Innovation Associate: Dr Rahil Alipour, [r.alipour@ucl.ac.uk](mailto:r.alipour@ucl.ac.uk)

---

### Local Setup

#### Previewing the GitHub Pages site with Jekyll

It's often useful to test the GitHub Pages site **locally** before pushing changes.
This lets you check that pages render correctly, links work, and styles look as expected without having to commit and wait for GitHub Pages to rebuild.

#### Prerequisites

You need **Ruby**, **Bundler**, and **Jekyll** installed. See the [GitHub guide on testing a Jekyll site locally](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) for full details.

**Ruby version:** Jekyll requires Ruby 3.1 or higher. We recommend managing Ruby versions with [rbenv](https://github.com/rbenv/rbenv) or [asdf](https://asdf-vm.com/) rather than using your system Ruby. You can check your version with:

```bash
ruby -v
```

> **macOS users:** do not use the system Ruby (`/usr/bin/ruby`) — you will hit permission errors. Install Ruby via rbenv or Homebrew first.

> **Windows users:** native Jekyll support on Windows is unreliable. We recommend using [WSL2](https://learn.microsoft.com/en-us/windows/wsl/) and following the Linux instructions within it.

---

#### Steps

1. Change into the `docs` directory (where the site lives):

```bash
cd docs
```

2. Install dependencies (only needed the first time, or after `Gemfile` changes):

```bash
bundle install
```

3. Serve the site locally:

```bash
bundle exec jekyll serve
```

4. Open your browser at:

```
http://127.0.0.1:4000/accord/
```

> **Note:** the site is served at `/accord/` (not just `/`) because of the `baseurl` setting in `_config.yml`. Going to `http://127.0.0.1:4000` will show a 404 — this is expected.

---

#### Troubleshooting

- **Changes not appearing?** Jekyll live-reloads content changes automatically, but changes to `_config.yml` or page front matter require a full restart (`Ctrl+C`, then `bundle exec jekyll serve` again).
- **Port already in use?** Run `bundle exec jekyll serve --port 4001` to use a different port.
- **Gem errors?** Try `bundle update` to refresh dependencies, then serve again.
