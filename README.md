# web-clock
A simple web page clock, made to run full screen in a browser on a TV.

It's a single file, `index.html`, with no dependencies.

## Usage

Open the page in a browser and switch to full screen (usually F11).

Deployed at: http://tower:8043/

### URL settings

Add these to the end of the URL. Combine them with `&`.

| Setting        | Effect                                                       |
|----------------|--------------------------------------------------------------|
| `?24h`         | Use 24-hour time (default is 12-hour with AM/PM)             |
| `?seconds=off` | Hide seconds (the time gets bigger to fill the space)        |
| `?date=off`    | Hide the date                                                |
| `?theme=NAME`  | Color theme: `red` (default), `cyan`, `amber`, `green`, `white` |
| `?weather=off` | Hide the temperature                                         |
| `?units=c`     | Show temperature in Celsius (default is Fahrenheit)          |
| `?lat=..&lon=..` | Weather location (default is Teaneck, NJ 07666)            |

Examples:

```
http://tower:8043/?24h
http://tower:8043/?seconds=off&theme=amber
http://tower:8043/?24h&seconds=off&date=off&theme=white
```

### Features

- Once a minute the clock slowly drifts to a nearby spot to prevent burn-in.
- The current temperature and condition appear under the date. They come from
  [Open-Meteo](https://open-meteo.com/) (free, no API key) and refresh every 10 minutes.
- The mouse cursor is hidden over the page.
- The page asks the browser to keep the screen awake. Browsers only allow this
  on HTTPS or localhost, so on a plain-HTTP server, set the TV or browser's
  own power settings to stay on.

## Deploying

Copy `index.html` to `\\tower\www\index.html`, then refresh the browser on the TV.
