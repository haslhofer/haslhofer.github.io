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

Python code:

- Python library **"aiohttp"** offers simple webserver. [Link to tutorial](https://docs.aiohttp.org/en/stable/web_quickstart.html#:~:text=In%20order%20to%20implement%20a%20web%20server%2C%20first,import%20web%20async%20def%20hello%28request%29%3A%20return%20web.Response%28text%3D%22Hello%2C%20world%22%29)

"`python
from aiohttp import web
ROOT = os.path.dirname(__file__)
"`

Define function that will deliver the html doc

`
async def index(request):
    content = open(os.path.join(ROOT, "index.html"), "r").read()
    return web.Response(content_type="text/html", text=content)
`