# Streams API Coding Challenge
The following describes the coding challenge for implementing a *Streams API*.  Please read entire document as as well as the entire [README.md](/README.md) before implementing and submitting your solution.

## Background
Our clients (mobile apps, web SPAs, connected TV apps on tvOS, Roku, FireTV, etc.) need to play Discovery video content to support our digital experiences.  To do this, they must issue HTTP requests to our Streams API which returns playback data used for rendering our custom-developed video players.

## Mission
Create your version of this *Streams API*.  Any requirements not explicitly specified is an opportunity to propose your own solution.

The API should support the following requests:
- `GET /v1/streams`
- `GET /v1/streams/{id}`

The API response for an individual resource should include the following attributes:
- **`id`** - Unique identifier for the stream resource
- **`streamUrl`** - HLS stream URL
- **`captions`** - Array of caption URLs and their associated caption type (vtt, scc)
- **`ads`** - Array of advertisement metadata

Your API response should resemble [the following JSON structure](/data/sample-api-response-with-ads.json). Note that multiple resources should simply be an array of these objects.

## Data Sources
**`id`**, **`streamUrl`** and **`captions`** are obtained from a database query.  You can find an export of the database for your development and testing [here](/data/streams-mongoexport.json).

**`ads`** are obtained by issuing an HTTP GET request to the following URL: `https://gruesome-rate-3945.nanoscaleapi.io/v1/codingchallenge/ads/{streamId}` where `streamId` is the same ID used for your implemented Streams API.
