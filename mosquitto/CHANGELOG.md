- Stop building libwebsockets (#3)

Mosquitto 2.1 has its own WebSocket server. The broker is built with
WITH_WEBSOCKETS=yes, which selects that server and does not link
libwebsockets. Only WITH_WEBSOCKETS=lws uses the library. The image has
built libwebsockets since the 2.1 upgrade without using it.

Remove the libwebsockets build, cmake and the Renovate entry for
libwebsockets.
