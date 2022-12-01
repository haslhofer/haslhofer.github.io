---
layout: post
title:  "WebRTC deconstruct"
author: gerald
categories: [ pivot ]
image: assets/images/landscape7.jpg
---

# WebRTC learnings

Analysis of https://github.com/tsonglew/webrtc-stream

## Setting up the webserver component

**Python code:**

- Python library **"aiohttp"** offers simple webserver. [Link to tutorial](https://docs.aiohttp.org/en/stable/web_quickstart.html#:~:text=In%20order%20to%20implement%20a%20web%20server%2C%20first,import%20web%20async%20def%20hello%28request%29%3A%20return%20web.Response%28text%3D%22Hello%2C%20world%22%29)

```
from aiohttp import web
ROOT = os.path.dirname(__file__)
```

Define function that will deliver the html doc

```
async def index(request): 
    content = open(os.path.join(ROOT, "index.html"), "r").read() 
    return web.Response(content_type="text/html", text=content)
```

Add to main part of python code
 
```
app = web.Application()
    ...
    app.router.add_get("/", index)
```

**What does Index.html do?**

Define two video elements

```
    <video id="localVideo" autoplay="true" playsinline="true"></video>
    <video id="serverVideo" autoplay="true" playsinline="true"></video>
```
Also add Js code
```
<script src="client.js"></script>
```

Retrieves webcam, and passes stream to local video instance

```
navigator.mediaDevices.getUserMedia({
	video: {
		height: 360,
		width: 480,
	}

}).then(stream => {
	localVideo.srcObject = stream;
	localVideo.addEventListener('loadedmetadata', () => {
		localVideo.play();
	});
});
```

When user clicks "start" button:

create RTC connection via Stun server
```
	var config = {
		sdpSemantics: 'unified-plan',
		iceServers: [{ urls: ['stun:stun.l..com:19302'] }]
	};

	pc = new RTCPeerConnection(config);

```
Then set the web cam stream to be transmitted onto the PeerConnction

```

    localVideo.srcObject.getVideoTracks().forEach(track => {
		pc.addTrack(track);
	});
```

Add event, if triggered, assigns the stream coming from the server:

```
pc.addEventListener('track', function (evt) {
		console.log("receive server video");
		if (evt.track.kind == 'video') {
			serverVideo.srcObject = evt.streams[0];
		}
	});
```
Start negotiation, then post the sdp/type to the webserver
