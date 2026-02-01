# Records Management

The Records page is your central database for all business information. Here you can view, search,
filter, and manage every company discovered through your searches.

<!-- Screenshot: Records page showing table with filters and selection -->

---

## Overview

Records are the core data entities in Ettutu V2. Each record represents a business found through
Google Places with enriched data from web crawling and AI analysis.

---

## Records Table

### Columns

| Column      | Description                                        |
| ----------- | -------------------------------------------------- |
| **Select**  | Checkbox for bulk actions                          |
| **Name**    | Business name                                      |
| **Website** | Company website (clickable)                        |
| **Email**   | Primary email address                              |
| **Phone**   | Phone number(s)                                    |
| **Status**  | Processing status (New, Crawled, Analyzed, Failed) |
| **Quality** | Lead quality score (High/Medium/Low)               |
| **Actions** | View, Edit, Delete buttons                         |

<!-- Screenshot: Records table columns with data -->

### Sorting

Click any column header to sort:

- **First click**: Sort ascending (A→Z, 0→9)
- **Second click**: Sort descending (Z→A, 9→0)
- **Third click**: Clear sort

Special sorting for data presence:

- Email column: Records WITH emails appear first
- Phone column: Records WITH phones appear first

See [Table Sorting](../General/Table%20Sorting.md) for details.

---

## Filtering Records

### Session Filter

Filter by search session to see only records from a specific search.

### Status Filter

| Filter              | Shows                            |
| ------------------- | -------------------------------- |
| **All Records**     | Active, non-deleted records      |
| **Not Crawled**     | New records without website data |
| **Fast Crawled**    | Processed by Fast crawler        |
| **Deep Crawled**    | Processed by Deep crawler        |
| **LLM Crawled**     | Processed by LLM crawler         |
| **🚫 Crawl Failed** | Records where crawling failed    |
| **Not Analysed**    | Not processed by AI analyzer     |
| **Analysed**        | AI analysis complete             |
| **🗑️ Recycled**     | Soft-deleted records             |

### Quality Filter

Filter by AI-assigned lead quality:

- **High** - Best prospects
- **Medium** - Good potential
- **Low** - Lower priority

### Text Search

Type in the search box to find records by name.

---

## Viewing Record Details

Click a record row or the View button to open the detail modal:

### Tabs

| Tab          | Content                                |
| ------------ | -------------------------------------- |
| **Overview** | Basic company info, location, ratings  |
| **Contact**  | Emails, phones, social media links     |
| **Analysis** | AI-generated descriptions and insights |
| **People**   | Associated contacts at the company     |
| **Notes**    | Your custom notes and tags             |
| **Raw Data** | Full JSON data from crawling           |

<!-- Screenshot: Record detail modal showing tabs -->

---

## Bulk Actions

Select multiple records using checkboxes, then use action buttons:

### Available Actions

| Action              | Description                            |
| ------------------- | -------------------------------------- |
| **Delete Selected** | Move selected records to Recycling Bin |
| **Add to Contacts** | Mark as verified contacts              |
| **Start Crawler**   | Run crawler on selected records        |
| **Start Analyzer**  | Run AI analysis on selected records    |
| **Export Selected** | Export to CSV                          |

### Selecting Records

- Click checkbox to select individual records
- Click header checkbox to select all on page
- Selection persists while filtering

---

## Processing Records

### Starting a Crawl

1. Select records to crawl
1. Click **Start Crawler** button
1. Choose crawler type:
   - **Fast** - Quick scan for basic contact info
   - **Deep** - Thorough multi-page crawl
   - **LLM** - AI-enhanced extraction
1. Monitor progress in Jobs page

### Starting Analysis

1. Select crawled records
1. Click **Start Analyzer**
1. AI processes website content
1. Results appear in record's Analysis tab

---

## Record Statuses

| Status        | Meaning                      |
| ------------- | ---------------------------- |
| **NEW**       | Just imported, not processed |
| **CRAWLING**  | Crawler currently running    |
| **CRAWLED**   | Website data extracted       |
| **ANALYZING** | AI analysis in progress      |
| **ANALYZED**  | Full processing complete     |
| **FAILED**    | Processing error occurred    |

---

## Deleting Records

### Soft Delete (Default)

- Click Delete → Record moves to Recycling Bin
- Can be restored later
- See [Recycling Bin](../Tools/Recycling%20Bin.md)

### Permanent Delete

- From Recycling Bin, delete again for permanent removal
- Cannot be undone

---

## Tips for Records Management

1. **Filter first** - Use filters to work with relevant subsets
1. **Batch process** - Select multiple records for bulk actions
1. **Check status** - Don't re-crawl already processed records
1. **Use quality filter** - Focus on high-quality leads first
1. **Clean up failed** - Review and retry or delete failed records

---

## Keyboard Shortcuts

| Key       | Action               |
| --------- | -------------------- |
| **↑/↓**   | Navigate rows        |
| **Enter** | Open selected record |
| **Esc**   | Close modal          |
| **Space** | Toggle row selection |

---

## Related Pages

- [Search Sessions](../General/Search%20Sessions.md)
- [Filters](../General/Filters.md)
- [Table Sorting](../General/Table%20Sorting.md)
- [Jobs Monitor](../Tools/Jobs%20Monitor.md)
- [Recycling Bin](../Tools/Recycling%20Bin.md)
