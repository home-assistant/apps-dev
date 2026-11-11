- Pass the interface list to jq as a variable (#11)

The interface list was produced by a nested jq call and spliced into
the text of the outer jq program. Pass it with --argjson instead, so
the program is a constant single-quoted string and needs no shell
escaping. The rendered options are unchanged.

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
