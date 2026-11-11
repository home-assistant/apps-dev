# Changelog since 4.0.0
- Move the s6 user bundle to user-bundles.d (#10)

s6-overlay 3.2.3.2, which the base image ships since 2026.11.0, reads
the user bundle from /etc/s6-overlay/user-bundles.d. Defining it under
s6-rc.d still works through a compatibility shim, but every start logs
a deprecation warning, and the shim goes away in the next major
s6-overlay release.

Move contents.d to user-bundles.d/user. Only the user bundle moves: the
mariadb and mariadb-lock bundles are the app's own and stay in s6-rc.d.
The user bundle's type file comes from the base image, and nothing
edits the bundle at runtime, so no script changes are needed.

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com> 
