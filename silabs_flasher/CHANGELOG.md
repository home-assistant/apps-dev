- Update base image to 3.14-alpine3.24-2026.11.1 (#12)

* Update base image to Alpine 3.24

Move from base-python 3.13-alpine3.23 to 3.13-alpine3.24 and update the
Renovate versionCompatibility pattern, so Renovate keeps following the
dated tags of the new Alpine base.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

* Update base image to Python 3.14

universal-silabs-flasher is tested upstream on Python 3.11 to 3.14, and
Home Assistant Core runs the same zigpy stack on 3.14.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

---------

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
