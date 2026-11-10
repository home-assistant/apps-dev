# Changelog since 3.4.0
- Move the s6 user bundle to user-bundles.d (#33)

s6-overlay 3.2.3.2, which the base image ships since 2026.10.0, reads
the user bundle from /etc/s6-overlay/user-bundles.d. Defining it under
s6-rc.d still works through a compatibility shim, but every start logs
a deprecation warning, and the shim goes away in the next major
s6-overlay release.

Move contents.d to user-bundles.d/user. The stage 2 hook removes
otbr-web and adds socat-otbr-tcp in that bundle, so point it at the new
location too: with the old path, its rm fails under errexit and
S6_BEHAVIOUR_IF_STAGE2_FAILS=2 halts the container. The type file comes
from s6-overlay's own user-bundles.d/user. 
