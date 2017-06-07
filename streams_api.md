# Streams API Coding Challenge
The following describes the coding challenge for implementing a *Streams API*.

## Background
Our clients (mobile apps, web SPAs, connected TV apps on tvOS, Roku, FireTV, etc.) need to play Discovery video content to support our digital experiences.  To do this, they must issue HTTP requests to our Streams API which returns playback data used for rendering our custom-developed video players.

## Mission
Create your version of this *Streams API*.  Any requirements not explicitly specified is an opportunity to propose your own solution.

The API should support the following requests:
- `GET /v1/streams`
- `GET /v1/streams/{id}`

The API response for an individual resource should include the following attributes:
- **streamUrl** - HLS stream URL
- **captions** - Array of caption URLs and their associated caption type (vtt, scc)
- **ads** - Array of advertisement metadata

Your API response should resemble [the following JSON structure](https://github.com/discovery-digital/svc-codingchallenge/blob/master/stubs/sample-api-response-with-ads.json). Note that multiple resources should simply be an array of these objects.

