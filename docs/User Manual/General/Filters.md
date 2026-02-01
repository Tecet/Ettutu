# Filters

Ettutu V2 provides powerful filtering options across the application to help you find exactly the
records you need.

<!-- Screenshot: Filter dropdown showing all options -->

---

## Overview

Filters help you:

- Focus on specific subsets of data
- Find records by processing status
- Identify records needing attention
- View deleted (recycled) records

---

## Records Page Filters

### Session Filter

Filter by search session to see only records from a specific Google Places search.

| Selection          | Shows                          |
| ------------------ | ------------------------------ |
| **All Sessions**   | Records from all searches      |
| **[Session Name]** | Only records from that session |

### Status/Crawler Filter

The main filter dropdown with processing status options:

| Filter              | Shows                            | Use Case                  |
| ------------------- | -------------------------------- | ------------------------- |
| **All Records**     | Active, non-deleted records      | Default view              |
| **Not Crawled**     | New records without website data | Find records to crawl     |
| **Fast Crawled**    | Processed by Fast crawler        | Review fast crawl results |
| **Deep Crawled**    | Processed by Deep crawler        | Review deep crawl results |
| **LLM Crawled**     | Processed by LLM crawler         | Review AI crawl results   |
| **🚫 Crawl Failed** | Records where crawling failed    | Troubleshoot issues       |
| **Not Analysed**    | Not processed by AI analyzer     | Find records to analyze   |
| **Analysed**        | AI analysis complete             | Review analyzed leads     |
| **🗑️ Recycled**     | Soft-deleted records             | Access recycling bin      |

### Quality Filter

Filter by AI-assigned lead quality:

| Filter            | Shows                         |
| ----------------- | ----------------------------- |
| **All Qualities** | Any quality score             |
| **High**          | High-quality leads            |
| **Medium**        | Medium-quality leads          |
| **Low**           | Low-quality leads             |
| **Not Scored**    | Records without quality score |

### Text Search

Type in the search box to filter by record name.

- Case-insensitive
- Partial matching
- Updates as you type

---

## Filter Combinations

Filters work together. Example combinations:

| Session           | Status          | Quality | Result                                   |
| ----------------- | --------------- | ------- | ---------------------------------------- |
| "London Plumbers" | Analysed        | High    | High-quality analyzed plumbers in London |
| All               | Not Crawled     | Any     | All records needing crawling             |
| Any               | 🚫 Crawl Failed | Any     | All failed crawls across sessions        |
| Any               | 🗑️ Recycled     | Any     | View recycling bin                       |

---

## Special Filters

### 🚫 Crawl Failed Filter

Shows records where the website crawler encountered errors:

**Common failure reasons:**

- Website offline or unreachable
- Blocked by robots.txt
- Timeout during crawl
- Invalid URL format
- SSL certificate issues

**Actions for failed records:**

- Retry crawl with different crawler
- Manually check website
- Delete if website doesn't exist

### 🗑️ Recycled Filter

Shows soft-deleted records in the Recycling Bin:

**What you can do:**

- **Restore** - Return record to active status
- **Permanent Delete** - Remove forever

See [Recycling Bin](../Tools/Recycling%20Bin.md) for details.

---

## Pipeline Filters

On the Pipeline (CRM) page:

| Filter          | Shows                        |
| --------------- | ---------------------------- |
| **All Stages**  | Leads in all pipeline stages |
| **New**         | Uncontacted leads            |
| **Contacted**   | Initial outreach made        |
| **Qualified**   | Confirmed fit                |
| **Proposal**    | Sent pricing                 |
| **Negotiation** | In discussions               |
| **Closed**      | Won or lost                  |

---

## Tasks Filters

On the Tasks page:

| Tab          | Shows           |
| ------------ | --------------- |
| **All**      | All tasks       |
| **My Tasks** | Assigned to you |
| **Today**    | Due today       |
| **Overdue**  | Past due date   |

| Status Filter   | Shows        |
| --------------- | ------------ |
| **Pending**     | Not started  |
| **In Progress** | Being worked |
| **Completed**   | Finished     |
| **Cancelled**   | Cancelled    |

---

## Jobs Filters

On the Jobs page:

| Status Filter | Shows             |
| ------------- | ----------------- |
| **All**       | Every job         |
| **Active**    | Currently running |
| **Queued**    | Waiting to start  |
| **Failed**    | Error state       |
| **Complete**  | Finished          |

| Type Filter   | Shows            |
| ------------- | ---------------- |
| **All Types** | All job types    |
| **Crawl**     | Website crawling |
| **Analyze**   | AI analysis      |
| **Export**    | Data exports     |

---

## Filter Behavior

### Default Filter

Most pages default to showing active (non-deleted) records.

### Filter Persistence

Filters reset when:

- Navigating away from page
- Refreshing browser
- Logging out

### Filter + Sort Interaction

1. Filter is applied first (reduces dataset)
1. Sort is applied to filtered results
1. Pagination shows filtered/sorted results

---

## Quick Filter Tips

1. **Start broad, then narrow** - Apply one filter at a time
1. **Use Recycled filter** - To access deleted records
1. **Combine status + quality** - Find best analyzed leads
1. **Check failed crawls** - Regular maintenance task
1. **Reset filters** - Select "All" options to clear

---

## Troubleshooting

### No Records Showing

- Check all filters are set to "All"
- Verify session has records
- Records may all be in recycling bin

### Wrong Records Showing

- Clear all filters first
- Apply filters one at a time
- Check for unexpected combinations

---

## Related Pages

- [Search Sessions](Search%20Sessions.md)
- [Records Management](../CRM/Records%20Management.md)
- [Table Sorting](Table%20Sorting.md)
- [Recycling Bin](../Tools/Recycling%20Bin.md)
