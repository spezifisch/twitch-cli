# [Twitch](https://twitch.tv) command line interface

## Features
* list followed channels
* list videos and active streams of channels
* [dmenu](https://tools.suckless.org/dmenu/) integration to select channels,
  videos or streams

## Example
The menu option makes for a simple Twitch GUI when paired
with a media player that support Twitch URLs
(I recommend [mpv](https://mpv.io/) and [youtube-dl](https://youtube-dl.org/)).
```shell
./cli.py --menu | xargs mpv
```

For a more sophisticated/klickety-klick GUI check out:
[streamlink-twitch-gui](https://streamlink.github.io/streamlink-twitch-gui/),
however it doesn't list videos (at the time of writing).

## Usage
```
usage: cli.py [-h] [--following] [--menu] [--menu-lines MENU_LINES]
              [--title-max-length TITLE_MAX_LENGTH] [--since SINCE]
              [CHANNEL [CHANNEL ...]]

Twitch command line interface

positional arguments:
  CHANNEL               channel to act on (defaults to followed channels)

optional arguments:
  -h, --help            show this help message and exit
  --following           print channels you're following
  --menu                run dmenu
  --menu-lines MENU_LINES
                        number of maximum lines in the menu
  --title-max-length TITLE_MAX_LENGTH
                        maximum length of printed titles
  --since SINCE         days to list videos
```
