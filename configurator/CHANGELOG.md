- Drop "dependency" from Renovate PR titles for Dockerfile ARGs (#6)

The ARG lines in the Dockerfile pin components of the image. Renovate
titled their PRs like this:

    Update dependency hass-configurator to v0.7.0

Use the component name as the commit message topic. The title becomes:

    Update hass-configurator to v0.7.0
