- Suppress ot-ctl "Done" output during OTBR configuration (#31)

* Suppress ot-ctl "Done" output during OTBR configuration

Wrap ot-ctl calls in otbr-agent-configure.sh in a helper which only
logs the ot-ctl output as a warning when a command fails, instead of
printing a bare "Done" line for each successful command.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

* Strip CR from ot-ctl output before checking for Done

The OpenThread CLI terminates lines with \r\n and ot-ctl passes them
through verbatim, so the output ends in "Done\r". Also note that
ot-ctl exits 0 on CLI errors, hence the output check.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

* Keep ot-ctl failures non-fatal and simplify Done check

Bashio runs scripts with errexit, so returning non-zero from the helper
would abort the configuration script on the first failing command.
Only log a warning instead. Compare against the output with all
whitespace removed to handle the CRLF line endings of the CLI.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

* Keep ot-ctl exit failures fatal

The previous change made all ot-ctl failures non-fatal, including when
ot-ctl itself fails (e.g. otbr-agent not reachable), which used to abort
the script via errexit. Restore that: return non-zero on ot-ctl exit
failures, and only log a warning for CLI errors, which ot-ctl reports
with exit status 0.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>

---------

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
