# My Garden — Zone 7 Potted Plant Care Tracker

## What this is

A self-contained HTML application for managing the care of a personal collection of potted plants in USDA Hardiness Zone 7. It runs entirely in the browser with no login, no backend, and no dependencies beyond an internet connection for the live weather feed.

The app was built to solve a specific problem: potted plants have materially different care requirements from the same species grown in the ground — they dry out faster, their roots are more vulnerable to freeze-thaw cycles, and they exhaust nutrients more quickly. Generic plant care advice does not account for this. The app provides care guidance that is explicitly calibrated for pot culture in zone 7.

---

## Features

- **Plant care database** — each plant has a dedicated care card covering watering frequency, watering amount, pruning season, pruning intensity, and pot-specific tips for zone 7, with a source citation for every field so advice can be cross-checked
- **Month-by-month calendar strip** — a visual indicator for each plant showing when to prune, when to water more frequently, and when to insulate the pot
- **Live weather monitor** — pulls current conditions (temperature, humidity, rainfall, UV index) for ZIP code 10025 from the Open-Meteo API, with a 1-hour cache to avoid redundant requests
- **Watering and frost alerts** — the weather monitor automatically flags when conditions require extra watering (high heat, low humidity, high UV) or when freezing temperatures put pot roots at risk, with the specific affected plants identified
- **Email alert system** — drafts a personalised plain-text alert email for the current conditions, ready to send via a mail service integration

---

## Plant list (v1.1)

23 plants across shrubs, trees, perennials, bulbs, vines, and ground covers:

Double Mock Orange · Red Dragon Japanese Maple · Double Knock Out Rose · Abelia Mucho Gusto · Weigela My Monet Purple Effect · Winter Red Winterberry · Clematis Jackmanii · English Ivy · Buddleia Prince Charming · Buddleia Buzz Midnight · Hibiscus White Chiffon · Lonicera Scentsation · Schizophragma Flirty Girl · American Elm · Yellow Daylily · Tiger Lily · Common Blue Violet · Hosta (August Lily) · Coral Honeysuckle · Campsis Radicans · Boston Ivy · Virginia Creeper · Boxwood

---

## Technical notes

- No API key required — weather data is provided by [Open-Meteo](https://open-meteo.com), a free and open-source weather API
- To send real email alerts, integrate a transactional mail service (SendGrid, Mailgun, etc.) and call their API with the composed email body
- To automate daily weather checks, a server-side cron job or cloud function would be needed; the browser-based app cannot self-schedule

---

## Release notes

### v1.1
- **Feed reckoner added** — a tool for gardeners using a hose-end sprayer to apply liquid plant food. Standard plant food instructions give dilution rates for watering cans (e.g. 1 tsp per gallon), but a hose-end sprayer works differently: it draws from a small concentrated reservoir and dilutes automatically via a dial setting. The reckoner takes the required concentration and reservoir fill volume (16 oz or 32 oz), and produces a reference grid showing the correct amount of concentrate to add for every common hose-end sprayer dial setting (in teaspoons, tablespoons, and fluid ounces). Amounts that correspond to neat, easily-measured quantities are highlighted for convenience.

### v1.0
- Initial release
- Plant care database for 20 potted plants, zone 7
- Simulated season-aware weather monitor
- Weather-triggered watering and frost alerts with affected plant identification
- Email alert composer
- Month-by-month calendar strip per plant
- Source citations on all care advice fields
