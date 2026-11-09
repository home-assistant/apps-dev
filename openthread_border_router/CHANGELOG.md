- Drop timestamp from settings migration script logs (#29)

The Supervisor now adds timestamps to the app logs (log_format: timestamp),
so the timestamp in the default coloredlogs format of the settings
migration script is redundant. Also drop the container hostname and PID,
which carry no useful information.

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
