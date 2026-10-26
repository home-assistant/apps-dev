- Update base image to Alpine 3.24 (#2)

The new base image brings git 2.54.0 and OpenSSH 10.3p1. The bashio,
s6-overlay and tempio versions are the same as in the 3.23 image.

DSA deployment keys stopped working in 8.0.0 already. That release
moved to Alpine 3.21, whose OpenSSH 9.9p2 is built without DSA support.
This update does not break them again, so it is not a breaking change.

Drop `dsa` from the `deployment_key_protocol` schema and document that
`dsa` keys do not work.
