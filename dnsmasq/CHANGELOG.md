- Update base image to Alpine 3.24 (#4)

Move the base image from 3.23-2026.11.0 to 3.24-2026.11.0. Point the
Renovate versionCompatibility rule at the 3.24 tags, so Renovate keeps
updating within the new Alpine line.

This bumps dnsmasq from 2.91 to 2.92rel2.
