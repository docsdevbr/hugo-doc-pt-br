---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Host on GitLab Pages
description: Host your site on GitLab Pages.
categories: []
keywords: []
aliases: [/hosting-and-deployment/hosting-on-gitlab/]
---

## Assumptions

- Working familiarity with Git for version control
- Completion of the Hugo [Quick Start]
- A [GitLab account](https://gitlab.com/users/sign_in)
- A Hugo website on your local machine that you are ready to publish

## BaseURL

The `baseURL` in your [site configuration](/configuration/) must reflect the full URL of your GitLab pages repository if you are using the default GitLab Pages URL (e.g., `https://<YourUsername>.gitlab.io/<your-hugo-site>/`) and not a custom domain.

## Configure GitLab CI/CD

Define your [CI/CD](g) jobs by creating a `.gitlab-ci.yml` file in the root of your project.

```yaml {file=".gitlab-ci.yml" copy=true}
variables:
  DART_SASS_VERSION: 1.85.0
  GIT_DEPTH: 0
  GIT_STRATEGY: clone
  GIT_SUBMODULE_STRATEGY: recursive
  HUGO_VERSION: 0.144.2
  NODE_VERSION: 23.x
  TZ: America/Los_Angeles
image:
  name: golang:1.23.4-bookworm

pages:
  script:
    # Install brotli
    - apt-get update
    - apt-get install -y brotli
    # Install Dart Sass
    - curl -LJO https://github.com/sass/dart-sass/releases/download/${DART_SASS_VERSION}/dart-sass-${DART_SASS_VERSION}-linux-x64.tar.gz
    - tar -xf dart-sass-${DART_SASS_VERSION}-linux-x64.tar.gz
    - cp -r dart-sass/ /usr/local/bin
    - rm -rf dart-sass*
    - export PATH=/usr/local/bin/dart-sass:$PATH
    # Install Hugo
    - curl -LJO https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb
    - apt-get install -y ./hugo_extended_${HUGO_VERSION}_linux-amd64.deb
    - rm hugo_extended_${HUGO_VERSION}_linux-amd64.deb
    # Install Node.js
    - curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION} | bash -
    - apt-get install -y nodejs
    # Install Node.js dependencies
    - "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
    # Build
    - hugo --gc --minify --baseURL ${CI_PAGES_URL}
    # Compress
    - find public -type f -regex '.*\.\(css\|html\|js\|txt\|xml\)$' -exec gzip -f -k {} \;
    - find public -type f -regex '.*\.\(css\|html\|js\|txt\|xml\)$' -exec brotli -f -k {} \;
  artifacts:
    paths:
      - public
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
```

## Push your Hugo website to GitLab

Next, create a new repository on GitLab. It is *not* necessary to make the repository public. In addition, you might want to add `/public` to your .gitignore file, as there is no need to push compiled assets to GitLab or keep your output website in version control.

```sh
# initialize new git repository
git init

# add /public directory to our .gitignore file
echo "/public" >> .gitignore

# commit and push code to master branch
git add .
git commit -m "Initial commit"
git remote add origin https://gitlab.com/YourUsername/your-hugo-site.git
git push -u origin master
```

## Wait for your page to build

That's it! You can now follow the CI agent building your page at `https://gitlab.com/<YourUsername>/<your-hugo-site>/pipelines`.

After the build has passed, your new website is available at `https://<YourUsername>.gitlab.io/<your-hugo-site>/`.

## Next steps

GitLab supports using custom CNAME's and TLS certificates. For more details on GitLab Pages, see the [GitLab Pages setup documentation](https://about.gitlab.com/2016/04/07/gitlab-pages-setup/).

[Quick Start]: /getting-started/quick-start/
