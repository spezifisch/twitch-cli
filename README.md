# [Twitch](https://twitch.tv) command line interface

## Features
* manage followed channels
* list videos and active streams of channels
* [dmenu](https://tools.suckless.org/dmenu/) integration to select channels,
  videos or streams
* manage stream metadata: title, category
* read chat

## Example
The menu option makes for a simple Twitch GUI when paired
with a media player that support Twitch URLs
(I recommend [mpv](https://mpv.io/) and [youtube-dl](https://youtube-dl.org/)).
```shell
twitch-cli --menu | xargs mpv
```

For a more sophisticated/klickety-klick GUI check out:
[streamlink-twitch-gui](https://streamlink.github.io/streamlink-twitch-gui/),
however it doesn't list videos (at the time of writing).

## Usage
```
usage: twitch-cli [-h] [--following] [--menu] [--json]
                  [--menu-lines MENU_LINES] [--chat] [--follow CHANNEL]
                  [--unfollow CHANNEL] [--title-max-length TITLE_MAX_LENGTH]
                  [--since SINCE]
                  [CHANNEL [CHANNEL ...]]

Twitch command line interface

positional arguments:
  CHANNEL               channel to act on (defaults to followed channels)

optional arguments:
  -h, --help            show this help message and exit
  --following           print channels you're following
  --menu                run dmenu
  --json                output json
  --menu-lines MENU_LINES
                        number of maximum lines in the menu
  --chat                interact with chat
  --follow CHANNEL      follow CHANNEL (may be used multiple times)
  --unfollow CHANNEL    unfollow CHANNEL (may be used multiple times)
  --title-max-length TITLE_MAX_LENGTH
                        maximum length of printed titles
  --since SINCE         days to list videos
```
### Stream manager
```
usage: twitch-cli --manage [-h] [--title] [--set-title TITLE] [--edit-title]
                           [--category] [--set-category CATEGORY] [--json]

Twitch stream manager command line interface

optional arguments:
  -h, --help            show this help message and exit
  --title               print stream title
  --set-title TITLE     set stream title
  --edit-title          edit stream title using $EDITOR
  --category            print stream category
  --set-category CATEGORY
                        set stream category
  --json                output json
```
