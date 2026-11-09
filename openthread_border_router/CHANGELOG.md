- Replace deprecated bashio addon functions with app equivalents (#30)

Use bashio::app.* instead of the deprecated bashio::addon.* aliases,
which log a deprecation warning. Also update user-facing banner text
from "add-on" to "app".

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com>
