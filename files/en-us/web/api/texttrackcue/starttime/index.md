---
title: "TextTrackCue: startTime property"
short-title: startTime
slug: Web/API/TextTrackCue/startTime
page-type: web-api-instance-property
browser-compat: api.TextTrackCue.startTime
---

{{APIRef("WebVTT")}}

The **`startTime`** property of the {{domxref("TextTrackCue")}} interface returns and sets the start time of the cue.

## Value

A number representing the start time, in seconds.

## Examples

In the following example a new {{domxref("VTTCue")}} (which inherits from `TextTrackCue`) is created starting at 0.1 second and ending at 0.9 seconds. The `startTime` property is then printed to the console.

```js
let video = document.querySelector("video");
let track = video.addTextTrack("captions", "Captions", "en");
track.mode = "showing";

let cue = new VTTCue(0.1, 0.9, "Hildy!");
console.log(cue.startTime); // 0.1
track.addCue(cue);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
