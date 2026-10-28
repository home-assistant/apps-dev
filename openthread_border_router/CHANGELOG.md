- Move dependency updates from Dependabot to Renovate (#1)

Renovate keeps the GitHub Actions updates Dependabot made: weekly, with
a 7 day cooldown, actions pinned to commit SHAs. It also tracks OTBR,
serialx, universal-silabs-flasher and the Home Assistant base image,
which Dependabot did not cover.

Pin the base image to a dated trixie tag with its digest, so Renovate
can update it within the Debian trixie line.

Add the ot-br-posix tag above each OTBR commit SHA, so Renovate can
update the tag and the SHA together. OTBR stable follows beta after
testing, so its updates wait for approval in the Dependency Dashboard.

The config builds on the Renovate setup of the apps repository [1]. The
base image rule comes from the plugin repositories [2].

[1] https://github.com/home-assistant/apps/pull/4837
[2] https://github.com/home-assistant/plugin-cli/blob/master/.github/renovate.json
