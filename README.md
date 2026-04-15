# how many chirps?

A field observation tool that estimates cricket chirping activity for any U.S. zip code using Dolbear's Law and real-time temperature data.

**Live site:** `https://yourusername.github.io/chirp-finder`

---

## what it does

Enter a U.S. zip code. The site fetches the current temperature for that location and applies Dolbear's Law — a formula published in 1897 by Tufts physics professor Amos Dolbear — to estimate how many times per minute a snowy tree cricket (*Oecanthus fultoni*) would be chirping there right now.

The classic version of the law: count chirps over 15 seconds, add 40, and you have the temperature in Fahrenheit. This site runs it in reverse.

---

## Dolbear's Law

```
N₆₀ = (T°F − 40) × 4
```

Where `N₆₀` is chirps per minute and `T°F` is the temperature in Fahrenheit. The formula applies specifically to the snowy tree cricket and is accurate to within 1–2°F between roughly 55°F and 95°F. Outside that range — too cold or too hot — cricket stridulation becomes unreliable and the linear relationship breaks down.

---

## data sources

- **Weather:** [Open-Meteo](https://open-meteo.com) — free, no API key required
- **Zip code geocoding:** [Zippopotam](https://api.zippopotam.us) — free, no API key required

Both APIs are called client-side directly from the browser. There is no backend, no server, and no data is stored or logged anywhere.

---

## tech

- Single `index.html` file — no build step, no dependencies, no npm
- Vanilla HTML, CSS, and JavaScript
- Animated birds via Canvas API
- Dithered countryside illustration in SVG using ordered dither patterns
- IBM Plex Mono via Google Fonts
- Fully responsive, mobile-friendly

---

## running locally

Just open `index.html` in a browser. No local server needed — the only external calls are to the two APIs above.

---

## deploying

This repo is configured for GitHub Pages. Any push to `main` updates the live site within ~60 seconds.

To set up GitHub Pages on a fork:
1. Go to Settings → Pages
2. Set source to `main` branch, `/ (root)` folder
3. Save — your site will be live at `https://yourusername.github.io/repo-name`

---

## limitations

- U.S. zip codes only
- Formula applies to snowy tree crickets specifically — other species have different chirp-rate constants
- Accuracy degrades below ~55°F (crickets go silent) and above ~95°F (heat stress)
- Zippopotam is a community-run free service with no uptime guarantee

---

*Dolbear's Law first published in The American Naturalist, 1897.*
