This project has been archived. Use these built-in commands instead:

```
pactl set-sink-volume @DEFAULT_SINK@ -5%
pactl set-sink-volume @DEFAULT_SINK@ +5%
pactl set-sink-mute @DEFAULT_SINK@ toggle
```

---

# PulseAudio volume

Adjust volume or toggle mute of all running PulseAudio sinks.  Ideal for binding to media keys.

Features:

- Doesn't change the volume of non-running sinks.
- Doesn't set the volume higher than 100%.

## Example usage

Increase volume by 5% (don't go above 100%):

```
pulseaudio_volume.py inc 5
```

Decrease volume by 10%:

```
pulseaudio_volume.py dec 10
```

Toggle mute (mute if unmuted, unmute if mute):

```
pulseaudio_volume.py toggle
```

## Example Awesome WM config snippet

```
awful.key({ }, "XF86AudioLowerVolume",  function () awful.util.spawn("pulseaudio_volume.py dec 5") end),
awful.key({ }, "XF86AudioRaiseVolume",  function () awful.util.spawn("pulseaudio_volume.py inc 5") end),
awful.key({ }, "XF86AudioMute",         function () awful.util.spawn("pulseaudio_volume.py toggle") end),
```

## Contributing

__Feel free to remix this piece of software.__ See [NOTICE](./NOTICE) and [LICENSE](./LICENSE) for license information.
