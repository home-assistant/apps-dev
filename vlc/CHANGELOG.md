- Convert startup scripts to s6-rc oneshots and modernize finish scripts (#5)

Replace the legacy cont-init.d scripts with init-secret and init-nginx
oneshots, so vlc and nginx declare their dependencies explicitly. Use
the /command/with-contenv shebang consistently.

Rework the finish scripts to record the exit code in the container
results like other apps do. VLC does not halt on SIGTERM since
pulse-monitor restarts it that way when the PulseAudio socket goes away.

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
