# Search Sessions

Search Sessions are the starting point for lead discovery in Ettutu V2. Using the Google Places API,
you can find businesses matching your criteria and automatically import them for enrichment.

<!-- Screenshot: Search Sessions page showing session cards -->

---

## Overview

The Searches page lets you:

- Create new business searches
- View all past search sessions
- Monitor crawl progress
- Manage session archives

---

## Creating a New Search

### Search Form Fields

| Field                   | Description                   | Example                                  |
| ----------------------- | ----------------------------- | ---------------------------------------- |
| **Query**               | Business type or keyword      | "plumber", "accountant", "dental clinic" |
| **Location**            | City, region, or area         | "London, UK", "Manchester"               |
| **Radius (km)**         | Search distance from location | 5, 10, 25                                |
| **Max Results**         | Maximum businesses to fetch   | 20, 50, 100                              |
| **Auto-Crawl**          | Start crawling automatically  | On/Off toggle                            |
| **Google Maps Account** | Which API key to use          | Select from configured accounts          |

<!-- Screenshot: New search form with all fields visible -->

### Starting a Search

1. Click **New Search** button
1. Fill in search query (e.g., "accountants")
1. Enter location (e.g., "Birmingham, UK")
1. Set radius (default: 10km)
1. Choose max results (default: 20)
1. Toggle Auto-Crawl if desired
1. Click **Search**

The search runs in the background. Results appear as a new session card.

---

## Session Cards

Each search creates a session card showing:

| Element      | Description                          |
| ------------ | ------------------------------------ |
| **Query**    | What you searched for                |
| **Location** | Where you searched                   |
| **Results**  | Total businesses found               |
| **Emails %** | Percentage with emails extracted     |
| **Status**   | Active, Completed, or Archived       |
| **Actions**  | Crawl, View Records, Archive buttons |

<!-- Screenshot: Individual session card with labels -->

---

## Session Actions

### Crawl Button

Starts the website crawler for all records in the session:

- Click **Crawl** to begin
- Progress modal shows completion
- Choose crawler type (Fast, Deep, LLM)

### View Records

Opens the Records page filtered to this session's businesses.

### Archive Session

Moves the session to archived state:

- Archived sessions don't appear in main view
- Can be restored later
- Records remain in database

---

## Session Filters

Filter the session list:

| Filter       | Shows                    |
| ------------ | ------------------------ |
| **Active**   | Current working sessions |
| **Archived** | Sessions you've archived |
| **All**      | Everything               |

---

## Monitoring Progress

While crawling is active:

- Session card shows live job count
- Progress bar updates automatically
- Emails % increases as data is extracted
- Click card to see detailed progress

---

## Best Practices

### Search Query Tips

| Good Queries         | Why                    |
| -------------------- | ---------------------- |
| "dental clinic"      | Specific business type |
| "family lawyer"      | Targeted profession    |
| "italian restaurant" | Niche category         |

| Poor Queries | Why                        |
| ------------ | -------------------------- |
| "business"   | Too generic, mixed results |
| "shop"       | Very broad category        |

### Location Tips

- Use city + country for best results: "Leeds, UK"
- Larger radius = more results but less relevant
- Start with 10km radius, expand if needed

### Workflow Tips

1. **Enable Auto-Crawl** for hands-off processing
1. **Use smaller max results** (20-50) for initial tests
1. **Archive completed sessions** to keep workspace clean
1. **Review emails %** before moving to analysis

---

## Google Maps Account Selection

If you have multiple Google Maps API accounts configured:

- Select account in search form dropdown
- Each account has separate quota
- Switch accounts when quota is low

Configure accounts in **Settings → Google Maps**.

---

## Troubleshooting

### No Results Found

- Check location spelling
- Try broader search terms
- Increase search radius
- Verify Google Maps account is active

### Crawl Not Starting

- Check worker status in Dashboard
- Verify Redis connection in Settings
- Try manual crawl from Records page

### Low Email Percentage

- Some businesses don't list emails
- Try Deep or LLM crawler for better extraction
- Check individual record details

---

## Related Pages

- [Dashboard](Dashboard.md)
- [Records Management](../CRM/Records%20Management.md)
- [Filters](Filters.md)
- [Jobs Monitor](../Tools/Jobs%20Monitor.md)
