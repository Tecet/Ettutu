# Table Sorting

All data tables in Ettutu V2 feature automatic sorting for easy data organization and discovery.
This guide explains how sorting works and how to use it effectively.

<!-- Screenshot: Table header showing sort indicators -->

---

## Overview

Tables throughout the application support:

- Click-to-sort on any column
- Ascending and descending order
- Smart sorting for complex data types
- Visual sort direction indicators

---

## How to Sort

### Basic Sorting

1. **Click column header once** → Sort ascending (A→Z, 0→9, Old→New)
1. **Click again** → Sort descending (Z→A, 9→0, New→Old)
1. **Click third time** → Clear sort, return to default order

### Visual Indicators

| Icon           | Meaning           |
| -------------- | ----------------- |
| ⬆️ ChevronUp   | Sorted ascending  |
| ⬇️ ChevronDown | Sorted descending |
| No icon        | Not sorted        |

---

## Sortable Columns

### Records Table

| Column             | Sort Behavior                           |
| ------------------ | --------------------------------------- |
| **Name**           | Alphabetical A→Z / Z→A                  |
| **Company**        | Alphabetical                            |
| **Website**        | Alphabetical by URL                     |
| **Email**          | Has email → No email                    |
| **Phone**          | Has phone → No phone                    |
| **Social Media**   | Has social → No social                  |
| **LinkedIn**       | Has LinkedIn → No LinkedIn              |
| **Created**        | Date/time oldest→newest / newest→oldest |
| **Crawl Status**   | By status value                         |
| **Crawler Type**   | By crawler name                         |
| **Analyst Status** | By status value                         |
| **CRM Status**     | By pipeline stage                       |

### People Table

| Column      | Sort Behavior                |
| ----------- | ---------------------------- |
| **Name**    | Alphabetical                 |
| **Role**    | Alphabetical                 |
| **Email**   | Has email → No email         |
| **Phone**   | Has phone → No phone         |
| **Company** | Alphabetical by company name |

### Non-Sortable Columns

- **Select** (checkbox column)
- **Actions** (button column)

---

## Special Sorting Functions

### "Has Data" Sorting

For optional fields like Email, Phone, Social Media:

**Ascending** (default click):

- Records WITH data appear first
- Records WITHOUT data appear last

**Descending** (second click):

- Records WITHOUT data appear first
- Records WITH data appear last

This is useful for:

- Finding records that need enrichment (sort descending)
- Working with complete records first (sort ascending)

### Array Field Sorting

Email and phone fields store multiple values as arrays:

```
emails: ['john@example.com', 'info@example.com']
phone: ['+44 123 456', '+44 789 012']
```

Sorting checks if the array has any content, not the specific values.

### Object Field Sorting

Social media stores as an object:

```
social_media: {
  linkedin: 'linkedin.com/in/john',
  twitter: 'twitter.com/john'
}
```

Sorting checks if any social media link exists.

---

## Use Cases

### Find Incomplete Records

Want to find records missing email addresses?

1. Click **Email** column header twice (descending)
1. Records without emails appear at top
1. Select them for re-crawling or manual lookup

### Find Latest Records

1. Click **Created** column header twice
1. Newest records appear at top
1. Review recent additions

### Find Analyzed Records

1. Click **Analyst Status** column header
1. Analyzed records appear first
1. Review AI-generated insights

### Find High-Quality Leads

1. Click **Quality** column header
1. High-quality leads appear first
1. Focus on best prospects

---

## Multi-Column Sorting

Currently, tables support single-column sorting only. Clicking a new column clears the previous
sort.

For complex filtering needs, use the filter dropdowns in combination with sorting.

---

## Persistence

Sort state is maintained while:

- Navigating pages (pagination)
- Applying filters
- Refreshing the page

Sort resets when:

- Leaving the page
- Logging out
- Clearing browser data

---

## Technical Details

### TanStack Table Integration

Ettutu V2 uses TanStack Table (React Table) for data display:

```typescript
const table = useReactTable({
  data,
  columns,
  state: { sorting },
  onSortingChange: setSorting,
  getCoreRowModel: getCoreRowModel(),
  getSortedRowModel: getSortedRowModel(),
  enableSorting: true,
});
```

### Custom Sort Functions

Special sorting functions handle complex data:

- `booleanSortingFn` - Has data vs no data
- `emailArraySortingFn` - Email array sorting
- `phoneArraySortingFn` - Phone array sorting
- `socialMediaSortingFn` - Social media object sorting

---

## Tips

1. **Sort before filtering** - Sorting applies to entire dataset
1. **Use for data quality** - Find incomplete records quickly
1. **Combine with pagination** - Sort then page through results
1. **Check column type** - Some columns have special sort behavior
