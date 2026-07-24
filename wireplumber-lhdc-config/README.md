# wireplumber-lhdc-config

WirePlumber configuration for the upstream LHDC v5 PipeWire plugin overlay.

It prepends `/usr/lib/spa-0.2-lhdc` to `SPA_PLUGIN_DIR`. WirePlumber's
default codec list remains unchanged, so all available Bluetooth codecs stay
enabled.

Restart WirePlumber after install:

```sh
systemctl --user daemon-reload
systemctl --user restart wireplumber
```
