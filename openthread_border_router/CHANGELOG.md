- Show timestamps in app logs by default (#13)

* Show timestamps in app logs by default

otbr-agent and the s6/bashio scripts log without their own timestamps.
Use the new Supervisor log_format option to have the Supervisor add
journal timestamps to the app logs by default. Older Supervisor versions
ignore the unknown key.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

* Don't prepend uptime to OpenThread log messages

The Supervisor now adds wall-clock timestamps to the app logs, which makes
the uptime prefix on OpenThread core log messages redundant.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

---------

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
