# Changelog since 4.1.0
- Drop "dependency" from Renovate PR titles for Dockerfile ARGs (#4)

The ARG lines in the Dockerfile pin components of the image. Renovate
titled their PRs like this:

    Update dependency Pulse-Eight/libcec to v8

Use the component name as the commit message topic. The title becomes:

    Update Pulse-Eight/libcec to v8 
