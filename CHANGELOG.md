# Changelog

## v1.2.0

- Added a Child Lock switch that prevents the physical side button from starting
  a manual feed while leaving Home Assistant and API feed requests available.

## v1.1.0

- Added motor pulse lockout for more reliable portion counting.
- Added Food State and Battery Pack Level entities.
- Centralized status LED behavior and RTTTL sound substitutions.
- Added dormant deep-sleep wake plumbing on the manual feed button.
- Fixed the Home Assistant blueprint feed confirmation wait so repeated feed
  completions are handled as fresh events.
- Made the blueprint Feeder State lookup tolerant of `sensor` and `text_sensor`
  entity domains.

## v1.0.0

- Initial public ESPHome package for the PETKIT Fresh Element Solo.
- Added Home Assistant blueprint for scheduled feeding, supervision, and
  notifications.
