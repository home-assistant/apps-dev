- Update universal-silabs-flasher to v1.3.0 and rework options (#9)

* Update universal-silabs-flasher to v1.3.0 and rework options

universal-silabs-flasher v1 replaced its CLI: --bootloader-baudrate,
--ezsp-baudrate and flash --force no longer exist, so the startup
script failed on every run with the new version.

Adapt the app to the new CLI:
- Replace bootloader_baudrate and ezsp_baudrate with probe_methods,
  bootloader_reset and profile, which map directly to flasher options.
- Drop flow_control, which was never read by the startup script.
- Make firmware_url mandatory and remove the bundled EmberZNet 7.4.4.0
  images. v1 has no version check, so the bundled images would always
  downgrade Yellow and ZBT-1.
- Let the flasher download the firmware itself.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

* Delete removed options from the stored configuration

Follow the developer documentation and delete bootloader_baudrate,
ezsp_baudrate and flow_control from the stored options on start, so
Supervisor stops warning that they do not exist in the schema.

Co-Authored-By: Claude Fable 5.2 <noreply@anthropic.com>

---------

Co-authored-by: Claude Fable 5.2 <noreply@anthropic.com>
