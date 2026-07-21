<div align="center">

<img src="icons/icon128.png" width="88" height="88" alt="RouteWave" />

# RouteWave

**London journeys, from wherever you already are.**

A free, open-source Chrome extension that turns an address on a web page into a clear London route — fastest, least walking, or step-free — with live arrivals, disruptions, and a word of warning when it is about to rain on your walk.

[![Licence: MIT](https://img.shields.io/badge/licence-MIT-0b1a33)](LICENSE)
[![Manifest V3](https://img.shields.io/badge/manifest-v3-dc241f)](manifest.json)
[![No trackers](https://img.shields.io/badge/trackers-none-0f7a4a)](PRIVACY.md)
[![Powered by TfL Open Data](https://img.shields.io/badge/data-TfL%20Open%20Data-0b1a33)](https://api-portal.tfl.gov.uk/)

[Install](#install) · [Privacy](https://wushu75.github.io/RouteWave/privacy.html) · [Report a problem](https://github.com/wushu75/RouteWave/issues/new/choose) · [Contributing](CONTRIBUTING.md)

</div>

---

> **Status: in testing.** Not yet on the Chrome Web Store. Load it unpacked using the steps below — it works fully today.

## What it does

| | Where |
| --- | --- |
| **Reads the page you are on** for postcodes, station names, street addresses and landmarks | Popup → **Read this page**, or right-click selected text |
| **Fastest, least walking, or fewest changes** | Popup → Plan |
| **Step-free routes**, street to vehicle and street to platform | Popup → Plan → **Step-free only** |
| **Live arrivals** for any stop or station | Popup → Live |
| **Line status and disruptions** across Tube, DLR, Overground, Elizabeth line and tram | Popup → Live |
| **Weather advice** tied to how much walking a route has — rain, ice, wind | Automatic, switchable off |
| **Share a route**: copy the text, copy a link, or use the system share sheet | Route card footer |
| **Favourite places and recent searches** | Popup → Saved |
| **Star rating and written review**, stored locally | Popup → Rate |

Nothing is uploaded. There is no account, no analytics, and no server of our own.


## TfL API notes

RouteWave uses the [TfL Unified API](https://api-portal.tfl.gov.uk/):

| Purpose | Endpoint |
| --- | --- |
| Stop and station search | `GET /StopPoint/Search/{query}` |
| Place search | `GET /Place/Search` |
| Journey planning | `GET /Journey/JourneyResults/{from}/to/{to}` |
| Live arrivals | `GET /StopPoint/{id}/Arrivals` |
| Line status | `GET /Line/Mode/{modes}/Status` |

An app key is optional. Without one you get TfL's anonymous rate limit, which is fine for personal use; add a free key in Settings if you hit it. A `300` response means TfL could not tell which place you meant, and RouteWave turns that into a "which one did you mean?" chooser rather than an error.

TfL data is used under the [TfL open data terms](https://tfl.gov.uk/info-for/open-data-users/our-open-data). Powered by TfL Open Data. Contains OS data © Crown copyright and database rights.

## Accessibility

Accessibility is part of the product, not a pass at the end.

- All colour pairings meet WCAG AA; body text on white and white on navy meet AAA
- Full keyboard operation, including arrow-key navigation for tabs and the star rating
- Visible focus rings on every interactive element, never suppressed
- Semantic roles: `tablist`/`tab`/`tabpanel`, `radiogroup` for ratings, `aria-live` for status so screen readers hear results as they load
- Step-free routing is a first-class option
- **Larger text** and **Reduce motion** settings, and `prefers-reduced-motion` honoured automatically
- Plain language throughout: "12 min", "3 changes", "due", "in 2 min"

Found a barrier? There is an [accessibility issue template](.github/ISSUE_TEMPLATE/accessibility.yml) — those are treated as bugs, not nice-to-haves.

## Contributing

Issues and pull requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first — the short version is: no dependencies, no bundler, no remote code, and no new permissions without a clear reason in the pull request.

## Licence

MIT

Powered by TfL Open Data. Weather data by [Open-Meteo](https://open-meteo.com/), used under CC BY 4.0. RouteWave is an independent project and is not affiliated with, endorsed by, or operated by Transport for London.
