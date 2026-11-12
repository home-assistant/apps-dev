- Use key=value form for ENV in Dockerfile (#5)

Docker build checks flag the legacy "ENV key value" form with the
LegacyKeyValueFormat warning.
