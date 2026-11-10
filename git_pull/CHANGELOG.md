# Changelog since 9.1.0
- git_pull: Mark deployment_key as password (#9)

deployment_key holds the private SSH key but was declared as a plain
string list, so the configuration UI showed it in clear text and API
consumers that redact format: password options returned it verbatim.

Declare the list elements as password. Existing configurations keep
working because password validates as a string.

Fixes #3

Co-authored-by: Claude Haiku 5.5 <noreply@anthropic.com> 
- git_pull: Only use deployment_key for SSH repositories (#8)

check-ssh-key split the repository URL on ":" and used the first part as
the SSH host. For HTTPS URLs that part is "https", so the app always ran
ssh against a host named "https", failed, and wrote the deployment key
into ~/.ssh even though the repository is not accessed via SSH.

Only run the SSH check and key setup when the repository is an SSH URL
(ssh://... or user@host:path). Extract the host correctly for both SSH
forms. For other URLs, log that deployment_key is not used.

Related to #4

Co-authored-by: Claude Haiku 5.5 <noreply@anthropic.com> 
- git_pull: Do not wipe /config when the clone fails (#7)

* git_pull: Do not wipe /config when the clone fails

git-clone removed the contents of /config before running git clone. If
the clone then failed (e.g. an HTTPS repository URL without credentials),
the existing configuration was lost, and the only copy was the backup in
/tmp.

Clone into a temporary directory first. Only once the clone succeeded
are /config backed up, cleared, and replaced with the cloned repository.
A failed clone now exits with /config untouched.

Fixes #4

Co-Authored-By: Claude Haiku 5.5 <noreply@anthropic.com>

* git_pull: Keep /config mode when copying the clone

The clone is made in a directory created by mktemp, which has mode 0700.
Copying "${CLONE_DIR}/." with cp -a also applied that directory's mode to
/config itself, changing the mode of the production configuration
directory.

Copy the entries of the clone directory one by one with find, so only
the cloned files are copied and /config keeps its own mode.

Co-Authored-By: Claude Haiku 5.5 <noreply@anthropic.com>

* git_pull: Use /config mode for the temporary clone directory

mktemp always creates the clone directory with mode 0700, and copying
the clone with cp -a applied that mode to /config.

Set the clone directory's mode to that of /config with chmod --reference
right after mktemp, and copy the clone with a single cp -a again. This
replaces the per-entry copy from the previous commit.

Co-Authored-By: Claude Haiku 5.5 <noreply@anthropic.com>

---------

Co-authored-by: Claude Haiku 5.5 <noreply@anthropic.com> 
- Update home-assistant/base image to 3.24-2026.11.0 (#5)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
