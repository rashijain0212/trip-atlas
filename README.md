# 2026 Road Trip Atlas

One page that gathers five road trips from 2026: a map of all the routes, the highlights of each trip, and a link to its full itinerary.

**Live site:** `https://<your-username>.github.io/<repo-name>/` (see [Publish it](#publish-it))

## The trips

| Dates | Trip | Getting there | Full itinerary |
|---|---|---|---|
| Jul 1-5 | New Mexico and Route 66 | Drove from Richardson, TX | Not published yet |
| Jul 27-30 | Buffalo River and Branson | Drove from Richardson, TX | Not published yet |
| Aug 21-25 | Colorado Rockies | Flew Dallas to Denver | [Colorado itinerary](https://rashijain0212.github.io/colorado/) |
| Sep 1-6 | Washington and Oregon | Flew Dallas to Seattle | [Seattle and Portland itinerary](https://rashijain0212.github.io/Seattle-and-Portland/) |
| Oct 10-19 | Nevada and California | Flew into Las Vegas, out of SFO | [Nevada and San Francisco itinerary](https://github.com/96rashijain/Nevada-San-Francisco) |

Five trips, 30 days, nine states.

## Why this repo exists

Each trip was planned in its own place: some as standalone sites, one as a repo, two only as documents. This repo is the front door. It answers three questions in one visit:

1. Where did we go, and when?
2. What were the stops that mattered on each trip?
3. Where is the complete day-by-day plan for each one?

It also works as a template. The next trip takes one new block in `index.html` and one new route on the map.

## What is in here

| File | Purpose |
|---|---|
| `index.html` | The whole site. HTML, CSS and a small script that draws the map. No build step and no dependencies. |
| `README.md` | This file. |

The only outside request is the Google Fonts stylesheet (Barlow, Barlow Condensed and IBM Plex Mono). If it fails to load, the page falls back to system fonts.

## Publish it

1. Create a new repository, for example `road-trips-2026`, and upload `index.html` and `README.md` to the root.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Update it

**Add a link to an itinerary.** Find the trip's `<article>` in `index.html`. Replace the dashed `Itinerary not published yet` label with:

```html
<a class="btn primary" href="YOUR-URL" target="_blank" rel="noopener">Full itinerary <span>&nearr;</span></a>
```

**Add a trip.** Copy one `<article class="trip">` block and edit the dates, route, highlights and link. Then, in the script at the bottom:

1. Add each new place to the `pl` object as `[latitude, longitude]`.
2. Add an entry to the `trips` array with an id, a color token and the ordered list of stops.
3. Define the color token (for example `--c-new`) in the light and both dark blocks at the top of the stylesheet.

**Change the look.** Colors and fonts are tokens at the top of the `<style>` block. The page follows the viewer's light or dark setting.

## Notes

- The routes on the map join the main stops with straight lines. They are not the roads driven.
- Booking references and confirmation numbers are deliberately left out.
