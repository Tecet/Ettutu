# People Directory

The People Directory provides a searchable database of individual contacts extracted from company
records. Find specific people, view their company associations, and manage your contact
relationships.

<!-- Screenshot: People Directory showing contact list with search -->

---

## Overview

While Records contain company information, the People Directory focuses on **individuals** - the
contacts, employees, and decision-makers discovered during website crawling.

---

## Accessing People Directory

Navigate to **Contacts** in the sidebar, then click the **People** tab in the navigation banner.

| View         | Shows                                |
| ------------ | ------------------------------------ |
| **Contacts** | Company records marked as contacts   |
| **People**   | Individual people from all companies |

---

## People List

Each person entry shows:

| Field        | Description                 |
| ------------ | --------------------------- |
| **Name**     | Person's full name          |
| **Role**     | Job title or position       |
| **Email**    | Email address               |
| **Phone**    | Phone number (if available) |
| **Company**  | Associated company name     |
| **LinkedIn** | LinkedIn profile link       |

<!-- Screenshot: People list showing columns and data -->

---

## Search Capabilities

The search box searches across multiple fields:

### Search by Person

| Search Term        | Finds                       |
| ------------------ | --------------------------- |
| "John Smith"       | People named John Smith     |
| "john@example.com" | People with that email      |
| "CEO"              | People with CEO in role     |
| "Manager"          | People with Manager in role |

### Search by Company

| Search Term      | Finds                                          |
| ---------------- | ---------------------------------------------- |
| "WBW Solicitors" | All people at WBW Solicitors                   |
| "WBW"            | Partial match - any company with "WBW"         |
| "Accountancy"    | People at companies with "Accountancy" in name |

### Search by Email Domain

| Search Term  | Finds                             |
| ------------ | --------------------------------- |
| "@wbw.co.uk" | All people with that email domain |
| "@gmail.com" | People using Gmail addresses      |

---

## Viewing Person Details

Click a person to see full details:

- **Contact Information** - All available contact methods
- **Company Link** - Click to view parent company record
- **Social Profiles** - LinkedIn, Twitter, etc.
- **Notes** - Any notes attached to this person

---

## Actions

### View Company

Click the company name or View Company button to open the associated record.

### Send to CRM

Push selected contacts to your CRM pipeline.

### Make Task

Create a follow-up task linked to this person.

---

## How People Are Created

People entries are automatically extracted during crawling:

1. **Crawler scans website** - Looks for team pages, about pages, contact pages
1. **Extracts contact info** - Names, roles, emails, phones
1. **Creates Person records** - Linked to parent company
1. **Searchable immediately** - Available in People Directory

### Data Sources

- Team/Staff pages
- About Us pages
- Contact pages
- Leadership sections
- LinkedIn data (when available)

---

## Data Integrity

### Cascade Delete Protection

When a company record is deleted:

- **Soft Delete** (Recycling Bin): People are preserved
- **Permanent Delete**: Associated people are automatically removed

This ensures no orphaned person records exist.

### Relationship

```text
Company Record (Parent)
  └── Person 1
  └── Person 2
  └── Person 3
```

---

## Use Cases

### Find All Contacts at a Company

1. Type company name in search
1. See all people associated with that company
1. Review roles to identify decision-makers

### Find People by Role

1. Search for role like "Director" or "Accountant"
1. See all people with that role across companies
1. Useful for targeting specific job functions

### Find Contacts by Email Domain

1. Search for "@companyname.com"
1. See all people with company email addresses
1. Filter out generic email addresses

---

## Response Format

Each person result includes:

```json
{
  "id": 123,
  "name": "Chris Hill",
  "role": "Director",
  "email": "chris@example.com",
  "phone": "+44 123 456 789",
  "linkedin": "linkedin.com/in/chrishill",
  "record_id": 146,
  "record_name": "Example Company Ltd",
  "record_website": "https://example.com",
  "record_is_lead": false,
  "record_crm": false
}
```

---

## Tips

1. **Search is case-insensitive** - "john", "John", "JOHN" all work
1. **Partial matching** - "Sol" finds "Solicitors"
1. **Multi-field search** - One search covers name, email, role, and company
1. **Sort by column** - Click headers to sort alphabetically

---

## Related Pages

- [Records Management](Records%20Management.md)
- [Projects](Projects.md)
- [Chat System](../Tools/Chat%20System.md)
- [Search Sessions](../General/Search%20Sessions.md)
