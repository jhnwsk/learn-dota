# Tracking Your Dota 2 Progress

How to use APIs to monitor your improvement over time.

---

## Available APIs

### 1. OpenDota API (Recommended for simplicity)

- **Free tier**: 50,000 calls/month, 60 requests/minute
- **Type**: REST API - easy to use with JavaScript fetch
- **Docs**: [docs.opendota.com](https://docs.opendota.com/)

#### Key Endpoints

| Endpoint | Description |
|----------|-------------|
| `/players/{steam_id}` | Profile info |
| `/players/{steam_id}/matches` | Match history |
| `/players/{steam_id}/heroes` | Hero-specific stats |
| `/players/{steam_id}/wl` | Win/loss record |
| `/players/{steam_id}/totals` | Aggregated stats |
| `/players/{steam_id}/counts` | Counts by category |

#### Example Request

```bash
curl "https://api.opendota.com/api/players/123456789/heroes"
```

### 2. STRATZ API

- **Free tier**: 2000 calls/hour (when logged in)
- **Type**: GraphQL - more flexible, slightly more complex
- **Docs**: [stratz.com/api](https://stratz.com/api)

STRATZ provides more detailed parsed replay data including ability usage statistics.

---

## Finding Your Steam ID

1. Go to [opendota.com](https://www.opendota.com/)
2. Search for your profile
3. Your Steam32 ID is in the URL: `opendota.com/players/YOUR_ID`

Alternatively, find it on your Steam profile URL and convert using a Steam ID converter.

---

## Metrics to Track for Improvement

Based on the [practice structure](06-practice-structure.md), here are the metrics that matter:

### Laning Phase (First 10 Minutes)
- Last hits at 10 minutes
- Denies
- Early deaths (should decrease over time)

### Hoodwink-Specific
- Win rate on Hoodwink over time
- KDA ratio (deaths indicate positioning issues)
- Stuns landed (Bushwhack, available in parsed matches)
- Damage dealt

### General Improvement
- Overall win rate trend
- Games played per week (consistency)
- Match duration patterns

---

## GitHub Pages Dashboard (TODO)

Build a static HTML/JS dashboard that:

1. Takes Steam ID from URL parameter
2. Fetches data from OpenDota API (client-side)
3. Visualizes trends using Chart.js

### Planned Features

- [ ] Hoodwink win rate over last 30 games
- [ ] KDA trend chart
- [ ] Games played calendar heatmap
- [ ] Last hits at 10 min average (parsed matches only)
- [ ] Comparison to previous week/month

### Technical Notes

- No backend required - pure client-side JavaScript
- OpenDota API supports CORS
- Use Chart.js or similar for visualizations
- Store Steam ID in localStorage for convenience

---

## Resources

- [OpenDota API Documentation](https://docs.opendota.com/)
- [OpenDota API Keys](https://www.opendota.com/api-keys)
- [STRATZ API](https://stratz.com/api)
- [STRATZ Knowledge Base](https://stratz.com/knowledge-base/API)
- [Chart.js](https://www.chartjs.org/) - for visualizations

---

## Next Steps

1. Find your Steam ID on OpenDota
2. Enable public match data in Dota 2 settings (Settings → Options → Expose Public Match Data)
3. Build the dashboard page in `stats/index.html`

---

[Back to Practice Structure](06-practice-structure.md) | [Back to README](README.md)
