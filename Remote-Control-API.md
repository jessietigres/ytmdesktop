First you need start the Remote Control.

Go to Settings and Integrations then enable Remote Control.

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

### Get info about lyrics
`GET http://localhost:9863/query/lyrics`

```js
"provider": String,
"data": String,
"hasLoaded": Bool
```

### Get info about playlist
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