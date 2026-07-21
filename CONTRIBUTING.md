# Contributing to RouteWave

Thanks for looking. RouteWave is a small, deliberately plain codebase — no build step, no dependencies, no framework — so getting from "I found a bug" to "I fixed it" is short.

## Ground rules

These are the constraints that keep the extension reviewable and trustworthy. A pull request that breaks one of them will be asked to change, however good the feature is.

1. **No dependencies and no bundler.** What you read in `src/` is exactly what Chrome runs.
2. **No remote code.** No CDNs, no `eval`, no dynamically fetched scripts, no external fonts. The Chrome Web Store rejects it, and so do we.
3. **No new permissions without a strong case.** Every permission has to be defended in the store listing. If a feature needs one, say so in the pull request and explain what breaks without it.
4. **No analytics, telemetry, accounts or tracking.** Ever. The privacy policy is a promise, not marketing.
5. **Accessibility is not optional.** Keyboard reachable, visible focus, sensible roles, AA contrast.

## Setting up

```bash
git clone https://github.com/wushu75/RouteWave.git
cd RouteWave
```

Then load it in Chrome:

1. Open `chrome://extensions`
2. Turn on **Developer mode**
3. **Load unpacked** → select the repository folder

After editing: popup and options changes just need the popup reopening. Changes to `src/background/service-worker.js` need the refresh arrow on the RouteWave card.

To see errors, right-click the popup and choose **Inspect**. The service worker has its own console, linked from the extension card.

## Where things live

| I want to change… | Look in |
| --- | --- |
| How routes are fetched or parsed | `src/lib/tfl.js` |
| How a route card looks | `src/popup/popup.js` (`routeCard`) and `src/popup/popup.css` |
| Colours, type, spacing, radii | `src/ui/tokens.css` |
| What counts as an address on a page | `src/content/detect.js` |
| Weather advice wording | `src/lib/weather.js` (`advise`) |
| Share text or links | `src/lib/share.js` |
| Saved data | `src/lib/storage.js` |
| Settings | `src/options/` |

## Before opening a pull request

```bash
bash scripts/build.sh
```

This validates the manifest, checks every referenced file exists, fails on remote code or `eval`, syntax-checks the JavaScript, and produces the store zip. Then load unpacked and click through the flow you touched.

## Writing user-facing text

Plain English, sentence case, no jargon, no exclamation marks. Say what happened and what to do about it. "No routes found. Try a nearby station, or turn off step-free to see more options." — not "Error: no results."

Never invent certainty about live data. If TfL did not return something, say so rather than guessing.

## Reporting bugs

Use the issue templates. If a route looks wrong, please check [TfL's own planner](https://tfl.gov.uk/plan-a-journey/) first — if it gives the same answer, the data comes from TfL. Still worth an issue if RouteWave presented it in a confusing way.

## Licence

By contributing you agree your work is released under the MIT Licence, the same as the rest of the project.
