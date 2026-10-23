# Home Assistant Apps: Development builds

> [!WARNING]
> This repository provides development builds for testing upcoming changes.
> Apps may fail to start, break after an update, or affect your Home Assistant system.
> Use these builds only if you are prepared to troubleshoot problems.
> For everyday use, choose the [official stable repository](https://github.com/home-assistant/apps).

Apps (formerly known as add-ons) for Home Assistant allow you to extend the functionality
around your Home Assistant setup. These apps can consist of an application
that Home Assistant can integrate with (e.g., a [MQTT broker](https://github.com/home-assistant/apps/blob/master/mosquitto/README.md) or [database server](https://github.com/home-assistant/apps/blob/master/mariadb/README.md))
or allow access to your Home Assistant configuration (e.g., via [Samba](https://github.com/home-assistant/apps/blob/master/samba/README.md) or using
the [File Editor](https://github.com/home-assistant/apps/blob/master/configurator/README.md)).

Apps can be installed and configured via the Home Assistant frontend on
systems that have installed Home Assistant.

[![Home Assistant - A project from the Open Home Foundation](https://www.openhomefoundation.org/badges/home-assistant.png)](https://www.openhomefoundation.org/)

## Installation

Add this repository in the Home Assistant app store using the following URL:

```text
https://github.com/home-assistant/apps-dev
```

## Apps provided by this repository

- **[CEC Scanner](/cec_scan/README.md)**

    Scan for HDMI CEC devices

- **[File editor](/configurator/README.md)**

    Simple browser-based file editor for Home Assistant

- **[Matter Server](/matter_server/README.md)**

    Matter WebSocket Server for Home Assistant Matter support.

- **[Terminal & SSH](/ssh/README.md)**

    Allow logging in remotely to Home Assistant using SSH

- **[Z-Wave JS](/zwave_js/README.md)**

    Control a Z-Wave network with Home Assistant Z-Wave JS

## Support

Got questions?

You have several options to get them answered:

- The [Home Assistant Discord Chat Server][discord].
- The Home Assistant [Community Forum][forum].
- Join the [Reddit subreddit][reddit] in [/r/homeassistant][reddit].

In case you've found a bug, please [open an issue on our GitHub][issue].

## Developing your own apps

In case you are interested in developing your own app, the
[official apps](https://github.com/home-assistant/apps) can be a great source of inspiration. For more information
about developing an app, please see our
[documentation for developers][dev-docs].

[discord]: https://www.home-assistant.io/join-chat
[forum]: https://community.home-assistant.io
[issue]: https://github.com/home-assistant/apps/issues
[reddit]: https://reddit.com/r/homeassistant
[dev-docs]: https://contributors.home-assistant.io/apps/
