# RouteWave privacy policy

**Last updated:** 21 July 2026 · **Version:** 1.0.0

This is the plain-text copy of the policy that ships with the extension at
`src/pages/privacy.html`. Both say the same thing.

## The short version

RouteWave has no servers, no accounts and no analytics. It does not collect,
store or sell your personal information. What you type stays in your browser,
except for the journey searches it must send to Transport for London to get you
an answer.

## What stays on your device

Saved in your browser profile with `chrome.storage.local`, never transmitted:

- Your settings, including your route preference and optional TfL app key
- Your favourite places
- Your recent searches
- Any star ratings or written reviews you save

You can download or erase all of it from the settings page at any time.

## What is sent, and where

| Sent to | What is sent | Why |
| --- | --- | --- |
| Transport for London (`api.tfl.gov.uk`) | The start and destination you typed, your route preference, and any stop name you look up | To plan journeys and return live arrivals and disruptions |
| Open-Meteo (`api.open-meteo.com`) | A coordinate rounded to roughly one kilometre; central London by default | To provide rain, ice and wind advice. Turning weather advice off stops the request entirely |

Neither request carries an identifier, an account, a cookie set by RouteWave, or
the contents of any page you visit.

## Reading web pages

RouteWave scans a page for London addresses and station names only when you
press **Read this page** or use the right-click menu on selected text. The scan
runs inside your browser, the results are shown only to you, and nothing from
the page is transmitted. There is no content script running in the background on
any site.

## Feedback and reviews

Ratings and comments are saved locally. Sending one is always a separate action:
you choose email, a GitHub issue or the Chrome Web Store review page, and you can
read the message first. RouteWave never transmits a review by itself.

## Children

RouteWave is a general travel tool, is not directed at children, and collects no
personal data from anyone of any age.

## Changes and contact

If this policy changes, the updated version ships with the extension and the date
above changes. Questions and concerns go to the issue tracker at
https://github.com/wushu75/RouteWave/issues — keeping them public means the
answers are searchable by the next person who asks. The full source code is
public too, so every claim on this page can be checked.
