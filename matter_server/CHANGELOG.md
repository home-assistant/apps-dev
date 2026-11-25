# Changelog since 9.3.0
- Update hassio-addons/bashio to v0.20.0 (#30)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Update home-assistant/workflows action to v0.1.2 (#29)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Update Matter Server to 1.6.0 (#25)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Move the s6 user bundle to user-bundles.d (#23)

s6-overlay 3.2.3.2, which this app installs directly, reads the user
bundle from /etc/s6-overlay/user-bundles.d. Defining it under
s6-rc.d still works through a compatibility shim, but every start logs
a deprecation warning, and the shim goes away in the next major
s6-overlay release.

Move contents.d to user-bundles.d/user. Service definitions and
dependencies stay in s6-rc.d.
The user bundle's type file comes from s6-overlay, and nothing
edits the bundle at runtime, so no script changes are needed. 
- Strip TypeScript files after installing a Matter Server from npm (#22)

When the app installs a beta or pinned Matter Server version at
startup, node_modules also contains TypeScript sources and declaration
files. Node never loads them, so they only use disk space (about
30 MB). The Matter Server Docker image deletes the same files
(matter-js/matterjs-server#1263). The .js.map files stay because the
server runs with --enable-source-maps.

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com> 
- Use bashio::app instead of deprecated bashio::addon (#17)

Co-authored-by: Claude Sonnet 5.5 <noreply@anthropic.com> 
