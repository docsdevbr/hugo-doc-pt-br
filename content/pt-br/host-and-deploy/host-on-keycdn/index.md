---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Host on KeyCDN
description: Host your site on KeyCDN.
categories: []
keywords: []
aliases: [/hosting-and-deployment/hosting-on-keycdn/]
---

[KeyCDN](https://www.keycdn.com/) provides a multitude of features to help accelerate and secure your Hugo site globally including Brotli compression, Let's Encrypt support, Origin Shield, and more.

## Assumptions

- You already have a Hugo page configured
- You have a GitLab account
- You have a KeyCDN account

## Create a KeyCDN Pull Zone

The first step will be to log in to your KeyCDN account and create a new zone. Name this whatever you like and select the [Pull Zone](https://www.keycdn.com/support/create-a-pull-zone/) option. As for the origin URL, your site will be running on [GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/getting_started_part_one.html) with a URL of `https://youruser.gitlab.io/reponame/`. Use this as the Origin URL.

![Screenshot of KeyCDN's pull zone creation page](keycdn-pull-zone.png)

While the origin location doesn't exist yet, you will need to use your new Zone URL address (or [Zone Alias](https://www.keycdn.com/support/create-a-zone-alias/)) in the `.gitlab-ci.yml` file that will be uploaded to your GitLab project.

Ensure that you use your Zone URL or Zone alias as the `BASEURL` variable in the example below. This will be the user-visible website address.

## Configure Your .gitlab-ci.yml File

Your `.gitlab-ci.yml` file should look similar to the example below. Be sure to modify any variables that are specific to your setup.

```yml
image: alpine:latest

variables:
    BASEURL: "https://cipull-7bb7.kxcdn.com/"
    HUGO_VERSION: "0.26"
    HUGO_CHECKSUM: "67e4ba5ec2a02c8164b6846e30a17cc765b0165a5b183d5e480149baf54e1a50"
    KEYCDN_ZONE_ID: "75544"

before_script:
    - apk update
    - apk add curl

pages:
    stage: deploy
    script:
    - apk add git
    - git submodule update --init
    - curl -sSL https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_${HUGO_VERSION}_Linux-64bit.tar.gz -o /tmp/hugo.tar.gz
    - echo "${HUGO_CHECKSUM}  /tmp/hugo.tar.gz" | sha256sum -c
    - tar xf /tmp/hugo.tar.gz hugo -C /tmp/ && cp /tmp/hugo /usr/bin
    - hugo --baseURL ${BASEURL}
    - curl "https://api.keycdn.com/zones/purge/${KEYCDN_ZONE_ID}.json" -u "${KEYCDN_API_KEY}:"
    artifacts:
    paths:
    - public
    only:
    - master
```

Using this integration method, you will have to specify the Zone ID and your [KeyCDN API](https://www.keycdn.com/api) key as secret variables. To do this, navigate to the top-left menu bar in GitLab and select Projects. Then, select your project and click on the Settings page. Finally, select Pipelines from the sub-menu and scroll down to the Secret Variable section.

The Secret Variable for your Zone ID should look similar to:

![Screenshot of setting the Zone ID secret variable](secret-zone-id.png)

While the Secret Variable for your API Key will look similar to:

![Screenshot of setting the API Key secret variable](secret-api-key.png)

While not strictly required, providing your Zone ID and API key is recommended for purging your zone. Without them, the CDN may continue serving outdated versions of your assets for an extended period.

## Push your changes to GitLab

Now it's time to push the newly created repository to GitLab:

```sh
git remote add origin git@gitlab.com:youruser/ci-example.git
git push -u origin master
```

You can watch the progress and CI job output in your GitLab project under “Pipelines”.

After verifying your CI job ran without issues, first check that your GitLab page shows up under `https://youruser.gitlab.io/reponame/` (it might look broken depending on your browser settings as all links point to your KeyCDN zone---don't worry about that) and then by heading to whatever Zone alias / Zone URL you defined.

To learn more about Hugo hosting options with KeyCDN, check out the complete [Hugo hosting with KeyCDN integration guide](https://www.keycdn.com/support/hugo-hosting/).
