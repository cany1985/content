---
title: Remote Playback API
slug: Web/API/Remote_Playback_API
page-type: web-api-overview
browser-compat: api.RemotePlayback
spec-urls: https://w3c.github.io/remote-playback/
---

{{DefaultAPISidebar("Remote Playback API")}}

The **Remote Playback API** extends the {{domxref("HTMLMediaElement")}} to enable the control of media played on a remote device.

## Concepts and Usage

Remote playback devices are connected devices such as TVs, projectors, or speakers. The API takes into account wired devices connected via HDMI or DVI, and wireless devices, for example Chromecast or AirPlay.

The API enables a page, which has an media element such as a video or audio file, to initiate and control playback of that media on a connected remote device. For example, playing a video on a connected TV.

> [!NOTE]
> Safari for iOS has some APIs which enable remote playback on AirPlay. Details of these can be found in [the Safari 9.0 release notes](https://developer.apple.com/library/archive/releasenotes/General/WhatsNewInSafari/Articles/Safari_9_0.html#//apple_ref/doc/uid/TP40014305-CH9-SW16).
>
> Android versions of Firefox and Chrome also contain some remote playback features. These devices will show a Cast button if there is a Cast device available in the local network.

## Interfaces

- {{domxref("RemotePlayback")}}
  - : Allows the page to detect availability of remote playback devices, then connect to and control playing on these devices.

### Extensions to other interfaces

- {{domxref("HTMLMediaElement.disableRemotePlayback")}}
  - : A boolean that sets or returns the remote playback state, indicating whether the media element is allowed to have a remote playback UI.
- {{domxref("HTMLMediaElement.remote")}} {{ReadOnlyInline}}
  - : Return a {{domxref("RemotePlayback")}} object instance associated with the media element.

## Examples

The following example demonstrates a player with custom controls that supports remote playback. Initially the button used to select a device is hidden.

```html
<video id="videoElement" src="https://example.org/media.ext">
  <button id="deviceBtn" class="hidden">Pick device</button>
</video>
```

```css
.hidden {
  display: none;
}
```

The {{domxref("RemotePlayback.watchAvailability()")}} method watches for available remote playback devices. If a device is available, use the callback to show the button.

```js
const deviceBtn = document.getElementById("deviceBtn");
const videoElem = document.getElementById("videoElement");

function availabilityCallback(available) {
  // Show or hide the device picker button depending on device availability.
  if (available) {
    deviceBtn.classList.remove("hidden");
  } else {
    deviceBtn.classList.add("hidden");
  }
}

videoElem.remote.watchAvailability(availabilityCallback).catch(() => {
  // If the device cannot continuously watch available,
  // show the button to allow the user to try to prompt for a connection.
  deviceBtn.style.display = "inline";
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
