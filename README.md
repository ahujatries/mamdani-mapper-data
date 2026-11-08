# mamdani-mapper-data

Data and scrapers behind [the Mamdani Mapper](https://raghavahuja.com/mamdani-mapper), a map of every public event NYC Mayor Zohran Mamdani's office has published.

Independent project. Not affiliated with the Mayor's Office or any campaign.

- `public/mamdani/events.json` — the data the site reads. One object per event: name, venue, lat/lng, borough, kind, date, source URL.
- `scripts/scrape-mamdani-schedule.mjs` — reads the [Mayor's Office press feed](https://www.nyc.gov/mayors-office/news). Claude pulls out the venue, Mapbox geocodes it. Runs hourly.
- `scripts/scrape-forward-schedule.mjs` — a daily Claude web search for events announced in advance.
- `public/mamdani/skip-cache.json` — releases already judged to have no in-person event, so they aren't re-checked.

Press releases give a date, not a time, so press events carry a noon placeholder start and `time_known: false`.

Wrong pin or missing event? Open an issue.
