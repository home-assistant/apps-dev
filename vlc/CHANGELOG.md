- Remove schema: false from config.yaml

The app linter requires schema to be an object. Supervisor validates
schema: false the same as the default empty schema, and the UI shows no
configuration for either.
