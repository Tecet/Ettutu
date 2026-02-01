# Projects

Projects is a full CRM project management system for organizing leads, tracking milestones, and
coordinating team efforts.

---

## Overview

### What Projects Offers

| Feature                | Description                        |
| ---------------------- | ---------------------------------- |
| **Lead Management**    | Link leads/records to projects     |
| **Milestones**         | Track progress with deadlines      |
| **Team Collaboration** | Assign members with roles          |
| **File Storage**       | Attach documents to projects       |
| **Activity Log**       | Complete audit trail               |
| **Chat Integration**   | Auto-created project channels      |
| **Templates**          | Start from pre-built project types |
| **Analytics**          | Dashboard with metrics             |

---

## Creating a Project

### From Scratch

1. Navigate to **CRM → Projects**
1. Click **+ New Project**
1. Fill in project details:
   - **Name** - Project title
   - **Description** - Overview and goals
   - **Status** - Planning, Active, On Hold, Completed, Cancelled
   - **Priority** - Low, Medium, High, Critical
   - **Due Date** - Target completion (optional)
1. Click **Create**

### From Template

1. Click **+ New Project**
1. Click **Use Template**
1. Select a template (e.g., Sales Pipeline, Lead Nurturing)
1. Template populates milestones and structure
1. Customize as needed
1. Click **Create**

---

## Project Status

| Status        | Meaning               |
| ------------- | --------------------- |
| **Planning**  | Project being defined |
| **Active**    | Work in progress      |
| **On Hold**   | Temporarily paused    |
| **Completed** | Successfully finished |
| **Cancelled** | Project terminated    |

---

## Team Members

### Adding Members

1. Open project detail
1. Click **Members** tab
1. Click **+ Add Member**
1. Search for user
1. Assign role
1. Click **Add**

### Member Roles

| Role            | Permissions                      |
| --------------- | -------------------------------- |
| **Owner**       | Full control, can delete project |
| **Manager**     | Manage members, edit settings    |
| **Contributor** | Add leads, files, notes          |
| **Viewer**      | Read-only access                 |

### Chat Sync

Project members automatically become members of the project's chat channel.

---

## Milestones

### Creating Milestones

1. Click **Milestones** tab
1. Click **+ Add Milestone**
1. Enter:
   - **Title** - Milestone name
   - **Description** - What needs to be achieved
   - **Due Date** - Target date
   - **Order** - Display order
1. Click **Save**

### Milestone Status

| Status          | Meaning           |
| --------------- | ----------------- |
| **Pending**     | Not started       |
| **In Progress** | Currently working |
| **Completed**   | Successfully done |
| **Overdue**     | Past due date     |

### Progress Tracking

- Milestones show completion percentage
- Project progress calculated from milestones
- Visual progress bar on project card

---

## Linking Leads

### Adding Leads to Project

1. Open project detail
1. Click **Leads** tab
1. Click **+ Link Leads**
1. Select leads from your records
1. Set lead status within project
1. Click **Link**

### Bulk Link from Records

1. Go to **Records** page
1. Select multiple records
1. Click **Actions → Add to Project**
1. Choose project
1. Confirm

### Lead Status in Project

| Status        | Meaning               |
| ------------- | --------------------- |
| **New**       | Just added            |
| **Contacted** | Initial outreach made |
| **Qualified** | Confirmed as viable   |
| **Proposal**  | Offer sent            |
| **Won**       | Converted             |
| **Lost**      | Did not convert       |

---

## Files

### Uploading Files

1. Click **Files** tab
1. Click **+ Upload**
1. Select file(s)
1. Add optional description
1. Click **Upload**

### File Types

- Documents (PDF, Word, Excel)
- Images (JPG, PNG, GIF)
- Archives (ZIP)

### File Organization

- Files can be categorized
- Search files by name
- Files from chat also appear here

---

## Notes

### Adding Notes

1. Click **Notes** tab
1. Click **+ Add Note**
1. Write your note (supports Markdown)
1. Click **Save**

### Note Features

- **Pin** important notes to top
- **Edit** your own notes
- **Search** across all notes
- **Timeline** view of all notes

---

## Activity Log

Every action is automatically logged:

| Activity       | Example                                       |
| -------------- | --------------------------------------------- |
| **Project**    | "Created project", "Changed status to Active" |
| **Members**    | "Added John as Contributor"                   |
| **Leads**      | "Linked 5 leads", "Marked lead as Won"        |
| **Milestones** | "Completed 'Initial Contact'"                 |
| **Files**      | "Uploaded proposal.pdf"                       |
| **Notes**      | "Added note"                                  |

### Viewing Activity

1. Click **Activity** tab
1. See full chronological history
1. Filter by activity type
1. Filter by team member

---

## Project Chat

### Auto-Created Channel

When you create a project, a chat channel is automatically created:

- Channel name matches project name
- All project members can access
- Discuss project-specific topics
- Share files directly to project

### Accessing Chat

1. Open project detail
1. Click **Chat** tab
1. Or find in sidebar under **Projects**

---

## Analytics Dashboard

### Project Metrics

| Metric         | Description            |
| -------------- | ---------------------- |
| **Lead Count** | Total leads in project |
| **Won/Lost**   | Conversion tracking    |
| **Progress**   | Milestone completion % |
| **Activity**   | Recent actions count   |

### Dashboard View

1. Go to **CRM → Projects**
1. View grid with all projects
1. See status indicators
1. Quick stats on each card

---

## Templates

### Available Templates

| Template           | Use Case             |
| ------------------ | -------------------- |
| **Sales Pipeline** | B2B sales process    |
| **Lead Nurturing** | Long-term follow-up  |
| **Event Campaign** | Event-based outreach |
| **Custom**         | Build your own       |

### Creating Templates (Admin)

1. Go to **Settings → Project Templates**
1. Click **+ New Template**
1. Define default milestones
1. Set default settings
1. Save template

---

## Best Practices

### Project Organization

1. **One project per campaign** - Keep focused
1. **Use milestones** - Break work into phases
1. **Link relevant leads** - Don't overload
1. **Regular updates** - Add notes on progress

### Team Collaboration

1. **Assign clear roles** - Viewers vs Contributors
1. **Use project chat** - Keep discussions in context
1. **Share files in project** - Not personal messages
1. **Check activity log** - Stay informed

### Lead Management

1. **Update lead status** - Track conversion
1. **Add from search sessions** - Bulk import
1. **Remove converted leads** - Keep list current
1. **Use Won/Lost** - Accurate reporting

---

## Keyboard Shortcuts

| Shortcut | Action        |
| -------- | ------------- |
| `N`      | New note      |
| `M`      | New milestone |
| `L`      | Link leads    |
| `C`      | Open chat     |

---

## Related Pages

- [Chat System](../Tools/Chat%20System.md) - Project channels
- [Records Management](Records%20Management.md) - Linking records
- [Search Sessions](../General/Search%20Sessions.md) - Finding leads


