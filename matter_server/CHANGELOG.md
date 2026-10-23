- Move dependency updates from Dependabot to Renovate (#1)

Renovate keeps the GitHub Actions updates Dependabot made: weekly, with
a 7 day cooldown, actions pinned to commit SHAs. It also tracks bashio,
tempio, s6-overlay and the matterjs-server base image, which Dependabot
did not cover.

Pin the matterjs-server base image to its digest, so Renovate can
update it along with the Matter Server version. The release procedure
now starts from the Renovate PR for the image.

The config builds on the Renovate setup of the apps repository [1].

[1] https://github.com/home-assistant/apps/pull/4837
