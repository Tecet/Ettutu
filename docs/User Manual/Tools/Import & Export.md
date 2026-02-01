# Import & Export

Ettutu V2 provides flexible options for importing data into the system and exporting your enriched
records to external tools and CRMs.

<!-- Screenshot: Export page showing format options and field selection -->

---

## Overview

| Feature             | Description                         |
| ------------------- | ----------------------------------- |
| **Import**          | Bring in records from CSV files     |
| **Export**          | Save records as CSV, JSON, or Excel |
| **CRM Integration** | Push to external CRM systems        |

---

## Export

### Accessing Export

1. Go to **Export** in sidebar
1. Or select records and click **Export Selected** in Records page

### Export Formats

| Format    | Description            | Best For                     |
| --------- | ---------------------- | ---------------------------- |
| **CSV**   | Comma-separated values | Spreadsheets, imports        |
| **JSON**  | Structured data format | APIs, developers             |
| **Excel** | Native .xlsx format    | Business users (coming soon) |

<!-- Screenshot: Export format selection dropdown -->

### Export Fields

Select which fields to include:

| Category     | Fields                               |
| ------------ | ------------------------------------ |
| **Basic**    | Name, Website, Address, Phone        |
| **Contact**  | Emails, Social Media, LinkedIn       |
| **Analysis** | Quality Score, Description, Industry |
| **Meta**     | Created Date, Status, Session        |

### Export Options

| Option          | Description                    |
| --------------- | ------------------------------ |
| **All Records** | Export entire database         |
| **Filtered**    | Export current filter results  |
| **Selected**    | Export checked records only    |
| **Session**     | Export specific search session |

### Export Process

1. Choose format (CSV/JSON)
1. Select fields to include
1. Choose record scope
1. Click **Export**
1. Download starts automatically

For larger exports, you can monitor progress in [Jobs Monitor](Jobs%20Monitor.md).

---

## Export History

View past exports:

| Column      | Description                |
| ----------- | -------------------------- |
| **Date**    | When export was created    |
| **Format**  | File format                |
| **Records** | Number of records exported |
| **Size**    | File size                  |
| **Action**  | Re-download button         |

<!-- Screenshot: Export history table -->

---

## Import

### Import Wizard

Step-by-step CSV import:

#### Step 1: Upload File

- Drag and drop CSV file
- Or click to browse
- Max file size: 10MB

#### Step 2: Field Mapping

Map CSV columns to record fields:

| CSV Column      | →   | Record Field |
| --------------- | --- | ------------ |
| "Company Name"  | →   | `name`       |
| "URL"           | →   | `website`    |
| "Email Address" | →   | `emails`     |
| "Phone"         | →   | `phone`      |

<!-- Screenshot: Field mapping interface -->

#### Step 3: Preview

- Review first 10 records
- Check field mapping accuracy
- Identify potential issues

#### Step 4: Import

- Confirm import
- Progress indicator shows completion
- Summary of imported records

Imports run as background jobs. If something looks stuck, check [Jobs Monitor](Jobs%20Monitor.md).

### Import Validation

Before importing, the system checks:

- ✅ Required fields present (name)
- ✅ URL format valid
- ✅ Email format valid
- ⚠️ Duplicate detection
- ⚠️ Missing optional fields

---

## CRM Integration

### Supported CRMs

| CRM            | Status     | Features      |
| -------------- | ---------- | ------------- |
| **Twenty CRM** | ✅ Active  | Full sync     |
| **Salesforce** | 🔜 Planned | Push contacts |
| **HubSpot**    | 🔜 Planned | Push contacts |

### Twenty CRM Export

Push records directly to Twenty:

1. Select records to export
1. Click **Send to Twenty**
1. Map fields to Twenty objects
1. Confirm push

---

## Quick Export from Records

Without leaving Records page:

1. Select records with checkboxes
1. Click **Export Selected** in toolbar
1. Choose format
1. Download immediately

See [Records Management](../CRM/Records%20Management.md) for selecting and bulk actions.

---

## Field Reference

### Available Export Fields

| Field                 | Description       | Type     |
| --------------------- | ----------------- | -------- |
| `id`                  | Record ID         | Number   |
| `name`                | Business name     | Text     |
| `website`             | Website URL       | URL      |
| `emails`              | Email addresses   | Array    |
| `phone`               | Phone numbers     | Array    |
| `address`             | Full address      | Text     |
| `rating`              | Google rating     | Number   |
| `review_count`        | Number of reviews | Number   |
| `status`              | Processing status | Text     |
| `lead_quality`        | Quality score     | Text     |
| `company_description` | AI description    | Text     |
| `industry_focus`      | Industry category | Text     |
| `created_at`          | Creation date     | DateTime |
| `updated_at`          | Last update       | DateTime |

---

## Best Practices

### Export Tips

1. **Filter first** - Export only what you need
1. **Choose relevant fields** - Don't export everything
1. **Use CSV for Excel** - Most compatible format
1. **Keep history** - Don't delete export history

### Import Tips

1. **Clean data first** - Fix formatting in CSV before import
1. **Test with small batch** - Import 10 records first
1. **Map carefully** - Double-check field mappings
1. **Handle duplicates** - Decide merge or skip

---

## Troubleshooting

### Export Issues

| Problem        | Solution                    |
| -------------- | --------------------------- |
| Download fails | Check browser popup blocker |
| Missing data   | Verify field selection      |
| Wrong encoding | Use UTF-8 CSV               |

### Import Issues

| Problem            | Solution                   |
| ------------------ | -------------------------- |
| File not accepted  | Check file is valid CSV    |
| Fields not mapping | Check column headers       |
| Duplicates created | Enable duplicate detection |
