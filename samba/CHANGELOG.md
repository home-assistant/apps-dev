- Show timestamps in app logs by default (#13)

smbd and nmbd log to stdout without any timestamp, and bashio only adds
the time of day. Set the Supervisor `log_format: timestamp` option so
every log line gets the journal timestamp.

With the Supervisor adding timestamps, drop the ones the app adds
itself: set LOG_FORMAT so bashio logs level and message only, and start
wsdd with --shortlog.

On Supervisor versions without log_format support, bashio and wsdd
messages no longer carry any time information.

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
