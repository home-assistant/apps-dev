- Print flashing progress as plain log lines (#11)

* Print flashing progress as plain log lines

universal-silabs-flasher v1 draws a tqdm progress bar that redraws
itself in place with carriage returns. In the app log every redraw ends
up as its own line, about 190 lines of bar characters per flash.

Configure tqdm through its environment variables to print a plain
progress line every 5 seconds, and strip the carriage returns from the
flasher output. Use pipefail so the flasher's exit code is kept.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

* Simplify progress output filtering

Drop the percentage and total from the progress line. The flasher
overshoots the firmware size on the last update, which needed a filter
loop to hide. With a plain byte count, tr is enough to strip the
carriage returns.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

---------

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
