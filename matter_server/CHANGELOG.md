# Changelog since 9.3.0
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
