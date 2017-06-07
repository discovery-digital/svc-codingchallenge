# Streams API Coding Challenge
The following describes the coding challenge for implementing a *Streams API*.

## Background
Our clients (mobile apps, web SPAs, connected TV apps on tvOS, Roku, FireTV, etc.) need to play Discovery video content to support our digital experiences.  To do this, they must issue HTTP requests to our Streams API which returns playback data used for rendering our custom-developed video players.

## Mission
Create your version of this *Streams API*.  Any requirements not explicitly specified is an opportunity to propose your own solution.

The API should support the following requests:
- `GET /v1/streams`
- `GET /v1/streams/{id}`

The API response for an individual resource should resemble the following JSON structure (multiple resources should simply be an array of these objects):
```javascript
{
  "streamUrl": "https://somecdn.com/0123456789.m3u8",
  "captions": {
    "vtt": {
      "en": "https://captionslocation.com/0123456789/captions.vtt"
    },
    "scc": {
      "en": "https://captionslocation.com/0123456789/captions.scc"
    }
  },
  "ads": {
    "breaks": [
      {
        "breakId": "0.0.0.125406899",
        "ads": [],
        "duration": 0,
        "timeOffset": 0,
        "position": "preroll",
        "type": "linear",
        "events": {
          "impressions": [
            "http://some-ad-server.com/ad/l/1"
          ]
        }
      },
      {
        "breakId": "mid0",
        "ads": [
          {
            "creative": "abcd1234",
            "duration": 30,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          },
          {
            "creative": "abcd1235",
            "duration": 40,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          },
          {
            "creative": "abcd1236",
            "duration": 20,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          }
        ],
        "duration": 90,
        "timeOffset": 553.07,
        "position": "midroll",
        "type": "linear",
        "events": {
          "impressions": [
            "http://some-ad-server.com/ad/l/1"
          ]
        }
      },
      {
        "breakId": "mid1",
        "ads": [
          {
            "creative": "abcd1237",
            "duration": 10,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          },
          {
            "creative": "abcd1238",
            "duration": 20,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          },
          {
            "creative": "abcd1239",
            "duration": 30,
            "events": {
              "impressions": [
                "http://some-ad-server.com/ad/l/1"
              ]
            }
          }
        ],
        "duration": 60,
        "timeOffset": 1212.0304583333,
        "position": "midroll",
        "type": "linear",
        "events": {
          "impressions": [
            "http://some-ad-server.com/ad/l/1"
          ]
        }
      }
    ],
    "breakOffsets": [
      {
        "timeOffset": 0,
        "index": 0
      },
      {
        "timeOffset": 553.07,
        "index": 1
      },
      {
        "timeOffset": 1212.0304583333,
        "index": 2
      }
    ]
  }
}
```
