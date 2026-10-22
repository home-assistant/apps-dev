- Move dependency updates from Dependabot to Renovate (#1)

Renovate keeps the GitHub Actions updates Dependabot made: weekly, with
a 7 day cooldown, actions pinned to commit SHAs. It also tracks libCEC
and the Home Assistant base image, which Dependabot did not cover.

Pin the base image to a dated 3.23 tag with its digest, so Renovate can
update it within the Alpine 3.23 line.

The config builds on the Renovate setup of the apps repository [1]. The
base image rule comes from the plugin repositories [2].

[1] https://github.com/home-assistant/apps/pull/4837
[2] https://github.com/home-assistant/plugin-cli/blob/master/.github/renovate.json
