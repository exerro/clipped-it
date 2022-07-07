# clipped-it

Recording/clipping software for Valorant adding a suite of auto-clipping tools
and full-game recordings.

## Features

### Full game recordings

At any time in a game, press a keybind to record the full game (including from
the start, not just from when you press it).

If you have a bad game, you can choose to review it *at the end* rather than
starting the recording early and manually deleting the majority of recordings
which you don't care about.

### Manual clips

Just like other software, clip the last X seconds. You can have multiple
keybinds for different clip lengths, so you can make a "short clip",
"long clip", "round clip" etc.

### Auto clips

Automatically make clips based on in-game events. Set it to record any round you
ace in, +/-10 seconds around a 3k in a round, any death less than 5s into a
round, and so on.

### Easy clip review/editing

See your recent clips and easily set their title, trim them, and make
fast-forward the less interesting sections within the clip.

### Third party integrations

Upload your clips to existing services such as Streamable from inside the app.

All your clips are stored as normal `.mp4` files and are easy to find so you can
use your favourite editing tools to make sick montages.

Metadata such as kills, deaths, round times, etc are stored in a companion file
which can be loaded by third party software or read by a human if you're really
bored.

## Mockups

![](mockups/Manual%20clips%20settings.png)
![](mockups/Clip%20notification.png)
![](mockups/New%20clips%20notification.png)
![](mockups/Clip%20editor.png)

## Technical details

I've not started development so this is mostly just notes.

### Recording options

https://www.bandicam.com/best-codec-for-recording-software/

Probs using ffmpeg for recording. Should support multiple codecs including H264.
Might want to use different codecs for "live game" (reduce additional lag, be
lossless) and for actual clips (optimise quality and storage size, don't care
about encoder efficiency).

Lazily handle clip encoding outside of critical game time (maybe during buy
phase, definitely during queues/post-match).
