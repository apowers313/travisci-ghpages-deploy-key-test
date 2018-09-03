## Overview
This repo is an example of how to deploy to [GitHub pages](https://pages.github.com/) using a [GitHub Deploy Key](https://developer.github.com/v3/guides/managing-deploy-keys/).


## Create Deploy Key

1. `ssh-keygen -t rsa -b 4096 -f ./travis_key` (no password)
2. Open https://github.com/apowers313/travisci-ghpages-deploy-key-test/settings/keys/new
3. Paste `travis_key.pub`

## Setup gh-pages

1. `npm init`
2. `npm install --save gh-pages`

## Config TravisCI

1. `sudo gem install travis`
2. `travis login` or `travis login --github-token <token>`
3. `travis encrypt-file travis_key`
4. Copy output line like `openssl aes-256-cbc -K ...` into `.travis.yml`
