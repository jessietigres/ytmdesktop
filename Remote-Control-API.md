First you need start the Remote Control.

Go to Settings and Integrations then enable Remote Control.

***
### Integrations made by people
Looking for a Integration which has already been made using the Remote Control API, here's a collection of a few which have been made by the community.

_We are not responsible for the usage of these Plugins, and Any issues caused by them_

- [OBS Now Playing](https://github.com/ytmdesktop/ytmdesktop/issues/441#issuecomment-822455379) - Display your Music within a Webpage to place inside of your OBS Layout to show while streaming/recording
- [StreamDeck](https://github.com/XeroxDev/YTMD-StreamDeck) - Display & Interact with YTM Desktop on a StreamDeck
- [TouchPortal](https://github.com/KillerBOSS2019/TP-YTDM-Plugin) - Display & Interact with YTM Desktop on a TouchPortal 
- [VSCode-YTMusic](https://github.com/sedders123/vscode-ytmusic) - Display & Interact with YTM Desktop as you Code in Visual Studio Code.

See page: https://ytmdesktop.app/external_integrations.html

***
### Get info about player and track
`GET http://localhost:9863/query`

```js
"player": {
    "hasSong": Bool,
    "isPaused": Bool,
    "volumePercent": Int,
    "seekbarCurrentPosition": Int,
    "seekbarCurrentPositionHuman": String,
    "statePercent": Int,
    "likeStatus": String,
    "repeatType": String
},
"track": {
    "author": String,
    "title": String,
    "album": String,
    "cover": String,
    "duration": Int,
    "durationHuman": String,
    "url": String,
    "id": String,
    "isVideo": Bool,
    "isAdvertisement": Bool,
    "inLibrary": Bool
}
```

### Get info about player
`GET http://localhost:9863/query/player`

```js
"hasSong": Bool,
"isPaused": Bool,
"volumePercent": Int,
"seekbarCurrentPosition": Int,
"seekbarCurrentPositionHuman": String,
"statePercent": Int,
"likeStatus": String,
"repeatType": String
```

### Get info about track
`GET http://localhost:9863/query/track`

```js
"author": String,
"title": String,
"album": String,
"cover": String,
"duration": Int,
"durationHuman": String,
"url": String,
"id": String,
"isVideo": Bool,
"isAdvertisement": Bool,
"inLibrary": Bool
```

### Get info about lyrics
`GET http://localhost:9863/query/lyrics`

```js
"provider": String,
"data": String,
"hasLoaded": Bool
```

### Get info about playlists
`GET http://localhost:9863/query/playlist`

```js
"list": [
    String,
    ...
]
```

### Get info about queue
`GET http://localhost:9863/query/queue`

```js
"automix": Bool,
"currentIndex": Int,
"list": [
    {
        "cover": String,
        "title": String,
        "author": String,
        "duration": String
    },
    ...
]
```

***

### Send command
`POST http://localhost:9863/query`

```js
"command": String,
"value": String (optional)
```
##### If server is protected with password, you need set **header**: `Authorization: Bearer PASSWORD`

#### command can be:
* `show-lyrics-hidden` - Open hidden lyrics window to provide data
* `track-play` - Play music
* `track-pause` - Pause music
* `track-next` - Next track
* `track-previous` - Previous track
* `track-thumbs-up` - Like current track
* `track-thumbs-down` - Dislike current track
* `player-volume-up` - Increase the player volume
* `player-volume-down` - Decrease the player volume
* `player-forward` - Forward 10 seconds
* `player-rewind` - Rewind 10 seconds
* `player-repeat` - Toggle `NONE` or `ONE` or `ALL`
* `player-shuffle` - Shuffle queue
* `player-add-library` - Add track to library
* `player-add-playlist` - Add track to playlist (**Needs value:** Playlist index)
* `player-set-seekbar` - Set value for seekbar (**Needs value:** 0 ~ Track duration)
* `player-set-volume` - Set value for volume (**Needs value:** 0 ~ 100)
* `player-set-queue` - Set index of queue to play track (**Needs value:** 0 ~ Queue length)