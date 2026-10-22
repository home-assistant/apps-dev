- Use a 5s startup healthcheck interval (#3)

File editor can stay in "Starting" for about 30s because of the default
healthcheck interval. On Docker Engine 25.0+, check every 5s during
startup while keeping normal polling at 30s. Older engines retain 30s
polling during startup.

Originally submitted as home-assistant/apps#4846.

Co-authored-by: ha-newbie <143764064+ha-newbie@users.noreply.github.com>
Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
