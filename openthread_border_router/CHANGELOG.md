- Drop timestamp from bashio log messages (#28)

The Supervisor now adds timestamps to the app logs (log_format: timestamp),
so the time-only prefix bashio adds to log messages of the startup scripts
is redundant. Override the bashio log format to omit it.

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
