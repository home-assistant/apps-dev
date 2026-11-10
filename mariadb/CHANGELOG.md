- Wait until the backup lock is held before reporting it (#9)

* Wait until the backup lock is held before reporting it

The pre backup command wrote FLUSH TABLES WITH READ LOCK to the lock
client and returned right away. If the statement had to wait for a
running query, Supervisor started copying the data directory while the
database was still being written to.

Let the client create a marker file after the statement and wait for
it. Give up after 60 seconds, since writes are blocked while the lock
is pending. Supervisor does not run the post backup command when the
pre command fails, so release the pending lock in that case.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

* Read the lock result from the client and stop the client on cleanup

Instead of a marker file, let the lock client print a result after the
FLUSH statement and read it from the client's stdout with a timeout.
The client now runs as a coprocess, so its stdout is reachable the same
way as its stdin.

Stopping the service left the client running. With a lock request still
waiting, new writes stayed blocked until the request was granted. Close
the client's input on stop so it quits, and terminate it if it is still
waiting for the lock, which cancels the request.

Use the same 30 seconds as the recorder does for its SQLite lock.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

* Let the server time out the lock request

Set lock_wait_timeout for the lock client, so the server cancels a pending
lock request itself and the client quits. The client service no longer
needs to stop the client on its own.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

---------

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
