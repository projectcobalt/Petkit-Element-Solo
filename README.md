# PETKIT Fresh Element Solo for ESPHome

ESPHome configuration and Home Assistant automation blueprint for the PETKIT
Fresh Element Solo feeder, model D4-2 / product code P570.

This is an independent community project. It is not affiliated with or endorsed
by PETKIT.

## ESPHome configuration

The repository's `petkit-element-solo.yaml` is a reusable factory/adoption
configuration. It:

- Uses the base node name `element-solo` with a MAC suffix so multiple feeders
  remain unique.
- Contains no Wi-Fi credentials, API encryption key, OTA password, or local IP
  address.
- Provides Wi-Fi provisioning through the fallback access point and captive
  portal.
- Advertises a `dashboard_import` URL so ESPHome can offer **Take Control**.

The advertised adoption package uses:

```text
github://projectcobalt/petkit-element-solo/petkit-element-solo.yaml@main
```

After flashing and provisioning the feeder, use **Take Control** in the ESPHome
dashboard. ESPHome will create an individual per-device YAML. Keep that managed
device YAML for future OTA updates; do not replace it with this generic factory
file.

Raw configuration URL:

```text
https://raw.githubusercontent.com/projectcobalt/petkit-element-solo/main/petkit-element-solo.yaml
```

## Home Assistant blueprint

The blueprint schedules and supervises feeding, verifies completion, and can
notify for jams, rejected feeds, power loss, low battery, or missing food-drop
pulses.

[Import the blueprint into Home Assistant](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fprojectcobalt%2Fpetkit-element-solo%2Fblob%2Fmain%2Fblueprints%2Fautomation%2Felement-solo-feeding.yaml)

Create one automation from the blueprint for each feeder. The ESPHome feed
action will be named similarly to:

```text
esphome.element_solo_a1b2c3_feed
```

## Important notes

- This configuration replaces the original PETKIT firmware.
- Confirm your hardware matches the supported model before flashing.
- The repository must remain public for `dashboard_import` and the Home
  Assistant blueprint import link to work.
- The default timezone is `Australia/Brisbane`; change the `time_zone`
  substitution for your location.

## Sources

- [ESPHome Devices: Petkit Fresh Element Solo Pet Feeder](https://devices.esphome.io/devices/petkit-fresh-element-solo-pet-feeder/)
- [n6ham ESPHome configuration](https://github.com/n6ham/esphome-configs/blob/master/petkit-fresh-element-solo.yaml)
- [Reddit: ESPHome on Petkit Solo Feeder](https://www.reddit.com/r/Esphome/comments/v19c7p/esphome_on_petkit_solo_feeder/)
- [Reddit: ESPHome on Petkit Solo Feeder, follow-up](https://www.reddit.com/r/Esphome/comments/108nqwc/esphome_on_petkit_solo_feeder_credits_to/)
- [ESPHome dashboard import documentation](https://esphome.io/components/dashboard_import/)
- [ESPHome factory firmware guidance](https://esphome.io/guides/creators/)
- [Home Assistant blueprint documentation](https://www.home-assistant.io/docs/blueprint/)
- [PETKIT Fresh Element Solo manual](https://instructions.petkit.com/D4_V1.2_20220713.pdf)
