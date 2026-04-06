# NAD Fork Notes

This fork exists to stabilize the `nad` Home Assistant custom integration used with a NAD T785 over Telnet.

## Included fixes

- Recreate the TCP/Telnet transport after a transport-level disconnect and retry the command once.
- Store coordinator runtime state in `hass.data` so the integration remains compatible across Home Assistant changes.
- Keep listener command state per coordinator instance instead of using a shared class-level list.
- Prevent `media_player` setup from crashing when `Main.Source` is temporarily unavailable during startup.
- Add defensive `None` checks around power, mute, and source command responses.

## HACS deployment

1. Push this repository to your own GitHub account.
2. In Home Assistant, open `HACS -> Integrations -> Custom repositories`.
3. Add your fork URL as category `Integration`.
4. Remove the old upstream `NAD` repository from HACS or stop updating it.
5. Install/update `NAD` from your fork.
6. Restart Home Assistant.

## Local environment note

The Home Assistant instance also had `pref_disable_polling` set to `false` for the NAD config entry in `/config/.storage/core.config_entries`. That setting lives in Home Assistant storage, not in this repository.
