# Streams API Coding Challenge
The following describes the coding challenge for implementing a *Streams API*.  Please read the entire document as well as the entire [README.md](/README.md) before implementing and submitting your solution.

## Background
Our clients (mobile apps, web SPAs, connected TV apps on tvOS, Roku, FireTV, etc.) need to play Discovery video content to support our digital experiences.  To do this, they must issue HTTP requests to our Streams API which returns playback data used for rendering our custom-developed video players.

## Mission
Create your version of this *Streams API*.  Any requirements not explicitly specified is an opportunity to propose your own solution.

The API should support the following requests:
- `GET /v1/streams/{id}`

The API response for an individual resource should include the following attributes:
- **`id`** - ID used to uniquely identify the stream resource
- **`streamUrl`** - HLS stream URL
- **`captions`** - Array of caption URLs and their associated caption type (vtt, scc)
- **`ads`** - Array of advertisement metadata typically obtained from an Ad API

Your API response should resemble [the following JSON structure](/data/sample-api-response-with-ads.json).

## Data Sources
**`id`**, **`streamUrl`** and **`captions`** - Attributes obtained from a database query.  You can find an export of the database for your development and testing [here](/data/streams.json).  Each individual stream resource has a corresponding document in Mongo.

**`ads`** - Attribute obtained by issuing an HTTP GET request to a 3rd party Ad API.  In place of a real Ad API, you may use this simplified API URL: https://coding-challenge.dsc.tv/v1/ads/{streamId} where `streamId` is the same ID used for your implemented Streams API.  This API will return ad metadata corresponding to the specified `streamId`.

Swagger/OpenAPI documentation of Ad API can be found [here](adapi-swagger.yaml).
