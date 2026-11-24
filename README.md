# web-clock
A simple web page clock, made to run full screen in a browser on a TV.

The clock is a single file, `index.html`, with no dependencies. A second file,
`configure.html`, is a settings page for building the clock's URL.

## Usage

Open the page in a browser and switch to full screen (usually F11).

Live at: https://meomaxy.github.io/web-clock/

### Settings page

Instead of typing the URL by hand, open [`configure.html`](https://meomaxy.github.io/web-clock/configure.html).
It has a toggle for each on/off setting, a color picker, a units choice, and a
location lookup by city or ZIP code (using Open-Meteo's geocoding). It shows a
live preview and a link that opens the clock with your choices. Copy that link
into the TV's browser.

### URL settings

Add these to the end of the URL. Combine them with `&`.

| Setting        | Effect                                                       |
|----------------|--------------------------------------------------------------|
| `?24h`         | Use 24-hour time (default is 12-hour with AM/PM)             |
| `?seconds=off` | Hide the seconds                                             |
| `?date=off`    | Hide the date                                                |
| `?theme=NAME`  | Color theme: `red` (default), `cyan`, `amber`, `green`, `white` |
| `?weather=off` | Hide the weather line (temperature, condition, precipitation) |
| `?units=c`     | Show temperature in Celsius (default is Fahrenheit)          |
| `?lat=..&lon=..` | Weather location (default is Teaneck, NJ 07666)            |

Examples:

```
https://meomaxy.github.io/web-clock/?24h
https://meomaxy.github.io/web-clock/?seconds=off&theme=amber
https://meomaxy.github.io/web-clock/?24h&seconds=off&date=off&theme=white
```

### Features

- The time is shown large, with the seconds as small digits after it (no colon)
  and a small superscript AM/PM. The date and weather use the same color as the time.
- Once a minute the clock slowly drifts to a new spot (up to about 8% of the screen
  width and 12% of the height) to prevent burn-in.
- The current temperature, condition, and today's chance of precipitation appear under the date. They come from
  [Open-Meteo](https://open-meteo.com/) (free, no API key) and refresh every 10 minutes.
- The mouse cursor is hidden over the page.
- The page asks the browser to keep the screen awake. Browsers only allow this
  on HTTPS or localhost, which the GitHub Pages URL satisfies. If the TV's
  browser doesn't support it, set the TV's own power settings to stay on.

## Deploying

The page is hosted with GitHub Pages, served from the root of the `main` branch.
Push to `main` and it redeploys automatically in a minute or so, then refresh the
browser on the TV.
