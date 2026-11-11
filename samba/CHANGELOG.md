- Pass the password to smbpasswd with printf (#8)

The password was piped to smbpasswd with echo. Bash's echo treats an
argument such as -n or -e as an option, so a password of that form was
swallowed and smbpasswd received empty input. printf with a %s format
passes any password through unchanged.

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
