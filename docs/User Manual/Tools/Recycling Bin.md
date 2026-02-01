# Recycling Bin and Delete System

The Recycling Bin is a safety feature that helps prevent accidental data loss by separating
"soft delete" (recoverable) from permanent deletion.

<!-- Screenshot: Recycling Bin page showing deleted records list -->

---

## Overview

The Ettutu V2 Delete System implements a **Two-Stage Deletion Process** (Soft Delete → Permanent
Delete) to prevent accidental data loss. This system is integrated throughout the application,
including inline actions and bulk operations.

## How It Works

### Step 1: Soft Delete (Move to Bin)

When you delete a normal record:

1. **Action**: User clicks "Delete" on a record.
1. **UI**: Shows a "Move to Recycling Bin?" confirmation.
1. **Backend**: Updates record with `is_deleted = true` and `deleted_at = timestamp`.
1. **Result**: Record disappears from the main list but remains in the database.

### Step 2: Permanent Delete

When you delete a record **already in the Recycling Bin**:

1. **Action**: User navigates to Recycling Bin, selects a record, and clicks "Delete".
1. **UI**: Shows a **Red Warning**: "This will permanently delete the record."
1. **Backend**: Hard deletes the row from the database.
1. **Result**: Data is unrecoverable.

## Bulk Operations

The system handles bulk deletions intelligently:

- **Bulk Soft Delete**: If you select normal records and delete them, they are all moved to the bin.
- **Bulk Permanent Delete**: If you select items _in the bin_, you can permanently wipe them.
- **Safety Check**: The system prevents mixing soft and permanent deletions in a single request to
  avoid ambiguity.

## REST API Reference

### Single Record

```http
# Soft Delete
DELETE /api/v2/records/{id}

# Permanent Delete
DELETE /api/v2/records/{id}?permanent=true
```

### Bulk Operations

```http
POST /api/v2/records/bulk
Content-Type: application/json

{
  "record_ids": [1, 2, 3],
  "operation": "delete",
  "params": {
    "permanent": false  // Set to true for permanent delete
  }
}
```

## Recovery

To recover accidental deletions:

1. Go to **User Manual → Tools → Recycling Bin** (or the Recycling Bin page in the app).
1. Find the record.
1. Click **Restore**.
1. The record re-appears in the main list with its original status and data intact.
