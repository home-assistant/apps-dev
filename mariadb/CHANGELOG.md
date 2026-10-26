- Update to Alpine 3.24 (MariaDB 11.4 to 11.8) (#5)

Note: This update upgrades MariaDB from 11.4 to 11.8. The database
migration will be performed automatically on the first startup after the
app is updated. Make a backup of the MariaDB app before installing this
update.

Alpine 3.24 updates MariaDB from 11.4.13 to 11.8.9. A data directory
created by 11.4 cannot be used by 11.4 again after the migration, so a
downgrade requires restoring the backup. Add 4.0.0 to breaking_versions
to stop automatic updates, like the 3.0.0 update did for MariaDB 11.4.

Update the Renovate versionCompatibility rule to stay on the Alpine 3.24
line of the base image.
