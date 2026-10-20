# Grab Offline Hours dashboard

N-Infinite CI dashboard for the Grab Merchant portal "Store Offline Hours" export.

## Folder layout

```
index.html               the dashboard (do not edit weekly)
data/offline_hours.csv   this week's Grab export (replace every week)
data/archive/            optional: keep past weeks here
```

## Weekly update (about 2 minutes)

1. In the Grab Merchant portal, download **Store Offline Hours** for last week (Mon–Sun).
2. Optional: copy last week's `data/offline_hours.csv` into `data/archive/` with its date range in the name.
3. Rename the new download to `offline_hours.csv` and upload it into `data/`, replacing the old file.
4. Commit. GitHub Pages refreshes in a minute or two. Hard-refresh the page (Ctrl+Shift+R) if you still see last week.

The title, date range, branch list, charts and action list all update from the CSV. No code changes needed.

## Notes

- Works for any brand with the same export format (columns: Merchant, Grab Service, Date, Offline Time (minutes), Scheduled Open Time (minutes), Offline Rate (%)).
- "Open another week's CSV" loads any export in the browser without uploading it (handy for comparing weeks or other brands).
- Opening `index.html` directly from your computer can't read `data/` (browser security); use the button or drag the CSV onto the page.
- Status rules: Chronic = in the report on 5+ days at 85%+ offline rate; Schedule glitch = every scheduled slot is 5 minutes or less; Occasional = everything else.
