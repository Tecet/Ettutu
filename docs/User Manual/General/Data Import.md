# Data Import

> [!info] Overview
> Import business records from CSV files directly into Ettutu with intelligent column mapping and flexible destination options.

---

## Quick Start

1. Navigate to **Settings** → **Import/Export**
2. Click **Import Data**
3. Follow the 4-step wizard

---

## Import Wizard Steps

### Step 1: Upload & Destination

![[import-step1.png]]

1. **Upload your CSV file** - drag & drop or click to browse
2. **Choose destination**:
   - **Records** - Import as new records for crawling and analysis
   - **Contacts** - Import as fully processed contacts (skip crawling)

> [!tip] When to use each destination
>
> - Use **Records** when you have raw company data that needs enrichment
> - Use **Contacts** when importing pre-vetted data with complete information

---

### Step 2: Column Mapping

![[import-step2.png]]

The system automatically suggests mappings based on your CSV headers.

**Available Actions:**

- **Link columns** - Select which Record field each CSV column maps to
- **Omit columns** - Choose "Do not import" for columns you don't need
- **Save template** - Save your mappings for future imports
- **Load template** - Apply previously saved mappings

**Required Fields:**

- `Name` - Company/business name (required)

**Optional Fields:**

- Address, Phone, Website, Email
- Rating, Categories
- Company Description, Notes, Tags

---

### Step 3: Preview

![[import-step3.png]]

Review how your data will look after import:

- View **5 sample records** with transformations applied
- Check for any data issues before committing
- Use **Back** button to adjust mappings if needed

---

### Step 4: Import Progress

![[import-step4.png]]

The import runs in the background:

- **Progress bar** shows completion percentage
- **Stats** display success/failed/skipped counts
- Large imports process in batches of 100 records

After completion:

- Click **View Records** or **View Contacts** to see imported data
- Failed rows are logged with error details

---

## Mapping Templates

Save frequently used column configurations:

1. Configure your mappings in Step 2
2. Click **Save Template**
3. Enter a name (e.g., "CRM Export Format")
4. Next import, select from the template dropdown

> [!note]
> Templates are saved globally and available for all future imports.

---

## Duplicate Handling

The system checks for duplicates using unique identifiers:

- **Skip duplicates** (default) - Existing records are not overwritten
- Duplicates are counted in the "Skipped" stats

---

## Troubleshooting

### Import fails with "Invalid CSV"

- Ensure file is valid CSV format (comma-separated)
- Check encoding (UTF-8 recommended)

### Records not appearing after import

- Check the correct destination was selected
- For Records: Look in Search Sessions → "Manual Import"
- For Contacts: Navigate to Contacts page

### Some rows failed

- Check the error log in Step 4
- Common issues: missing required fields, invalid data formats

---

## See Also

- [[Records]]
- [[Contacts]]
- [[Data Export]]
