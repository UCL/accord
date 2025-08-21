# ACCoRD – A Community for Contract Regulation for Data

ACCoRD public repository for the GitHub pages.

⚠️ Please do not include any private or sensitive data here – this is a public-facing repository.

ACCoRD aims to address barriers in data access and contracting that delay or block research using the UK’s federated Digital Research Infrastructure (DRI). Data contracts are often complex, bespoke, and inconsistent, causing delays of up to 9 months and making data sharing costly and inefficient.

For ACCoRD project management, a private repository, please go to: [accord_project_management](https://github.com/UCL-ARC/accord_project_management)

### Team

- Project Lead: Dr Michelle Harricharan, [m.harricharan@ucl.ac.uk](mailto:m.harricharan@ucl.ac.uk)
- Project Co-Lead: Dr Claire Ellul, [c.ellul@ucl.ac.uk](mailto:c.ellul@ucl.ac.uk)
- Project Co-Lead: Dr James Wilson, [j.a.j.wilson@ucl.ac.uk](mailto:j.a.j.wilson@ucl.ac.uk)
- Research & Innovation Associate: Katie Buntic, [k.buntic@ucl.ac.uk](mailto:k.buntic@ucl.ac.uk)
- Professional Enabling Staff: Dr Rahil Alipour, [r.alipour@ucl.ac.uk](mailto:r.alipour@ucl.ac.uk)

### Local Setup

#### Previewing the GitHub Pages site with Jekyll

It’s often useful to test the GitHub Pages site **locally** before pushing changes.  
This lets you check that pages render correctly, links work, and styles look as expected without having to commit and wait for GitHub Pages to rebuild.

To test this GitHub Pages site locally before deploying, you need **Ruby**, **Bundler**, and **Jekyll** installed.  
See the [GitHub guide on running a Jekyll site locally](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) for more details.

---

**Steps (after installing Ruby, Bundler and Jekyll):**

1. Change into the docs directory (where the site lives):

```bash
   cd docs
```

2. Install the required gems within `docs` (only once):

```bash
   gem install bundler jekyll
```

3. From `/docs` (where the `Gemfile` lives), install dependencies:

```bash
   bundle install
```

4. Serve the site locally:

```bash
   bundle exec jekyll serve
```

5. Open your browser at http://127.0.0.1:4000
