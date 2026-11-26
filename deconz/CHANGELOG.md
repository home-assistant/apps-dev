# Changelog since 8.8.1
- Increase stop timeout to 120 seconds (#9)

deCONZ flushes its SQLite database with fsync on shutdown. On slow
storage that is busy writing back other data, e.g. right after the
image of an update was pulled, this can take far longer than the
default 10 seconds. Docker then sends SIGKILL, which cannot interrupt
the fsync either, and the stop fails with "tried to kill container,
but did not receive an exit event", leaving the update in a failed
state.

Give the container up to 120 seconds to shut down gracefully.

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com> 
