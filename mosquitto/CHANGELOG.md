- Move dependency updates from Dependabot to Renovate (#2)

Renovate keeps the GitHub Actions updates Dependabot made: weekly, with
a 7 day cooldown, actions pinned to commit SHAs. It also tracks
Mosquitto, libwebsockets, mosquitto-go-auth and the Home Assistant base
image, which Dependabot did not cover.

Pin the base image to a dated trixie tag with its digest, so Renovate
can update it within the Debian trixie line.

The config builds on the Renovate setup of the apps repository [1]. The
base image rule comes from the plugin repositories [2].

[1] https://github.com/home-assistant/apps/pull/4837
[2] https://github.com/home-assistant/plugin-cli/blob/master/.github/renovate.json
