# Configuration

The Settings page provides centralized configuration for all Ettutu V2 system settings,
integrations, and user management.

<!-- Screenshot: Settings page main menu -->

---

## Accessing Settings

Click **Settings** in the sidebar navigation to access all configuration options.

---

## Settings Sections

| Section               | Purpose                           |
| --------------------- | --------------------------------- |
| **General**           | App name, timezone, basic options |
| **LLM Providers**     | AI model configuration            |
| **LLM Specialists**   | Role-based LLM assignment         |
| **Crawlers**          | Plugin configuration              |
| **Google Maps**       | API account management            |
| **Email (SMTP)**      | Email sending setup               |
| **Data & Backup**     | Database management               |
| **Users**             | User account management           |
| **API Documentation** | Link to Swagger docs              |

---

## General Settings

Basic application configuration:

| Setting      | Description                |
| ------------ | -------------------------- |
| **App Name** | Display name in header     |
| **Timezone** | Default timezone for dates |
| **Language** | Interface language         |

---

## Google Maps Configuration

Manage your Google Places API accounts for search functionality.

<!-- Screenshot: Google Maps accounts list -->

### Adding an Account

1. Go to **Settings → Google Maps**
1. Click **Add Account**
1. Enter account name (for identification)
1. Paste your API key
1. Click **Save**

### Account Fields

| Field          | Description                         |
| -------------- | ----------------------------------- |
| **Name**       | Friendly name (e.g., "Primary API") |
| **API Key**    | Google Places API key               |
| **Quota Used** | Requests used this month            |
| **Status**     | Active/Inactive                     |

### Getting a Google API Key

1. Go to [Google Cloud Console](https://console.cloud.google.com)
1. Create or select a project
1. Enable **Places API**
1. Go to **Credentials**
1. Create API key
1. (Recommended) Restrict to Places API only

### Managing Multiple Accounts

Use multiple API keys to:

- Spread quota across accounts
- Separate dev/production usage
- Handle different billing

Select account when creating searches.

---

## Email Configuration (SMTP)

Configure outbound email for notifications and exports.

### SMTP Settings

| Field          | Description         | Example                |
| -------------- | ------------------- | ---------------------- |
| **SMTP Host**  | Mail server address | smtp.gmail.com         |
| **SMTP Port**  | Server port         | 587                    |
| **Username**   | Account username    | your@email.com         |
| **Password**   | Account password    | App password           |
| **From Email** | Sender address      | noreply@yourdomain.com |
| **TLS**        | Enable encryption   | Yes (recommended)      |

### Testing Email

1. Configure SMTP settings
1. Click **Send Test Email**
1. Enter recipient address
1. Check inbox for test message

---

## Data & Backup

Database management and backup options.

<!-- Screenshot: Data & Backup section -->

### Backup

| Action              | Description                |
| ------------------- | -------------------------- |
| **Create Backup**   | Generate database backup   |
| **Download Backup** | Save backup file locally   |
| **Auto Backup**     | Schedule automatic backups |

### Restore

1. Click **Restore from Backup**
1. Upload backup file
1. Confirm restore
1. Wait for completion

⚠️ **Warning**: Restore replaces all current data.

### Data Management

| Action             | Description            |
| ------------------ | ---------------------- |
| **Clear Records**  | Delete all records     |
| **Clear Sessions** | Delete search sessions |
| **Reset Database** | Full database reset    |

---

## User Management

Manage user accounts and permissions.

<!-- Screenshot: User management table -->

### User List

| Column         | Description            |
| -------------- | ---------------------- |
| **Name**       | User's display name    |
| **Email**      | Login email address    |
| **Role**       | User role (Admin/User) |
| **Status**     | Active/Inactive        |
| **Last Login** | Most recent activity   |

### User Roles

| Role      | Permissions                            |
| --------- | -------------------------------------- |
| **Admin** | Full access, user management, settings |
| **User**  | Standard access, no settings           |

### Adding Users

1. Click **Add User**
1. Enter name and email
1. Set initial password
1. Select role
1. Click **Create**

### Editing Users

1. Click user row
1. Update details
1. Click **Save**

### Deactivating Users

1. Click user row
1. Toggle **Active** to off
1. User cannot login but data preserved

---

## Crawler Configuration

Configure crawler plugins and their parameters.

### Viewing Crawlers

1. Go to **Settings → Crawlers**
1. See list of available crawlers
1. Click crawler to view details

### Crawler Types

| Crawler  | Description               | Speed    |
| -------- | ------------------------- | -------- |
| **Fast** | Quick contact extraction  | ~10 sec  |
| **Deep** | Multi-page thorough crawl | ~60 sec  |
| **LLM**  | AI-enhanced extraction    | ~120 sec |

### Editing Crawler Parameters

1. Click **Edit** on crawler
1. Modify JSON configuration
1. Save changes

### Crawler Info Modals

| Modal              | Content                        |
| ------------------ | ------------------------------ |
| **Edit Modal**     | Adjust parameters              |
| **Strategy Modal** | View crawler methodology       |
| **Info Modal**     | Shared mechanics documentation |

---

## API Documentation

Quick access to API reference.

### Swagger UI

Click **API Documentation** to open Swagger UI at `/docs`.

Features:

- All endpoint documentation
- Try-it-out functionality
- Request/response schemas
- Authentication info

### API Sections

| Section      | Endpoints              |
| ------------ | ---------------------- |
| **Auth**     | Login, logout, session |
| **Records**  | CRUD operations        |
| **Searches** | Search management      |
| **Jobs**     | Queue operations       |
| **People**   | Contact directory      |
| **Pipeline** | CRM stages             |
| **Export**   | Data export            |
| **Settings** | Configuration          |

See [API Reference](../../03.%20Developer%20Guide/Backend/API%20Reference.md) for details.

---

## Related Pages

- [LLM Providers](LLM%20Providers.md)
- [Search Sessions](../General/Search%20Sessions.md)
- [Jobs Monitor](../Tools/Jobs%20Monitor.md)

---

## Plugin Configuration

Advanced plugin settings via JSON schemas.

### Accessing Plugin Config

1. Go to **Settings → Crawlers** (or other plugin type)
1. Click **Configure** on plugin
1. JSON schema form appears
1. Modify settings
1. Save

### Configuration Storage

Plugin configurations stored in database and applied at runtime.

---

## Troubleshooting Settings

### Settings Not Saving

- Check browser console for errors
- Verify you have Admin role
- Try refreshing page

### API Key Invalid

- Verify key is correct
- Check key isn't expired
- Ensure key has proper permissions

### Email Not Sending

- Verify SMTP credentials
- Check firewall allows outbound SMTP
- Try different port (587 vs 465)
