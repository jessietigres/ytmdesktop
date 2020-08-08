First you need start the Remote Control.

Go to Settings and Integrations then enable Remote Control.

***
#### Query info about player and track
`GET localhost:9863/query`

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