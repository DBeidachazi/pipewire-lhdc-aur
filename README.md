# pipewire-lhdc-aur

AUR packaging recipes for LHDC v5 Bluetooth playback through PipeWire.

## Packages

- `liblhdcv5`: builds the AOSP Android 17 LHDC v5 encoder as a normal Linux shared library.
- `pipewire-bluez5-lhdc-git`: builds an out-of-tree PipeWire bluez5 SPA plugin from `DBeidachazi/pipewire` with LHDC v5 enabled.
- `wireplumber-lhdc-config`: prepends `/usr/lib/spa-0.2-lhdc` to `SPA_PLUGIN_DIR` and enables `lhdc_v5` in WirePlumber's Bluetooth codec list.
- `pipewire-lhdc-meta`: convenience package that depends on the three active packages above.
- `lhdc-v5-helper`: deprecated transition package.

## Install

```sh
yay -S pipewire-lhdc-meta
systemctl --user daemon-reload
systemctl --user restart wireplumber
```

Reconnect the headset after restarting WirePlumber.

## Package Relationship

```text
liblhdcv5
  -> pipewire-bluez5-lhdc-git
      -> wireplumber-lhdc-config
          -> pipewire-lhdc-meta
```

The active implementation links PipeWire to the native `liblhdcv5` library.
