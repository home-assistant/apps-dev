# Changelog since 6.3.0
- Update home-assistant/base image to 3.24-2026.10.3 (#8)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Drop "dependency" from Renovate PR titles for Dockerfile ARGs (#6)

The ARG lines in the Dockerfile pin components of the image. Renovate
titled their PRs like this:

    Update dependency hass-configurator to v0.7.0

Use the component name as the commit message topic. The title becomes:

    Update hass-configurator to v0.7.0 
