# Chat System

The Chat System provides AI-powered assistance and team collaboration tools. It combines LLM
assistants with real-time team messaging.

<!-- Screenshot: Chat interface showing conversation and mode toggle -->

---

## Overview

The Chat system includes:

- **LLM Assistant** - Work and General modes for AI assistance
- **Team Channels** - Internal team communication
- **Context Channels** - Chat linked to projects, leads, or records
- **File Sharing** - Upload and share files in channels
- **Real-time Messaging** - WebSocket-powered instant updates

---

## Channel Types

| Type        | Description                   | Auto-Created              |
| ----------- | ----------------------------- | ------------------------- |
| **LLM**     | AI assistant conversations    | No                        |
| **Team**    | Internal team channels        | No                        |
| **Project** | Linked to a project           | Yes, when project created |
| **Lead**    | Linked to a lead/record       | On first access           |
| **Contact** | Direct messages between users | On first message          |

---

## Accessing Chat

Click **Chat** in the sidebar navigation to open the chat interface.

---

## LLM Assistant Modes

### Work Mode

Focused on your Ettutu data and business operations:

| Capability        | Example                                      |
| ----------------- | -------------------------------------------- |
| **Data Queries**  | "Show me all leads in London"                |
| **Record Lookup** | "Find records with emails from @company.com" |
| **Analytics**     | "How many records were added this week?"     |
| **Task Help**     | "What leads haven't been contacted?"         |

<!-- Screenshot: Work mode conversation example -->

### General Mode

General-purpose AI assistant:

| Capability    | Example                                     |
| ------------- | ------------------------------------------- |
| **Questions** | "What's the best time to send cold emails?" |
| **Advice**    | "How should I approach a CFO?"              |
| **Writing**   | "Help me draft an introduction email"       |
| **Research**  | "What industries are growing in the UK?"    |

<!-- Screenshot: General mode conversation example -->

### Switching Modes

Toggle between modes using the mode selector at the top of the chat interface.

---

## Chat Interface

### Components

| Element             | Description                              |
| ------------------- | ---------------------------------------- |
| **Message Input**   | Type your message here                   |
| **Send Button**     | Submit your message                      |
| **History Sidebar** | Past conversations (toggle to show/hide) |
| **Mode Toggle**     | Switch Work/General mode                 |
| **New Chat**        | Start fresh conversation                 |

### Sending Messages

1. Type your question or request
1. Press **Enter** or click **Send**
1. Wait for AI response
1. Continue the conversation

---

## Conversation History

### Managing Conversations

| Action             | How                               |
| ------------------ | --------------------------------- |
| **New Chat**       | Click "New Chat" button           |
| **Resume Chat**    | Click conversation in sidebar     |
| **Delete Chat**    | Click delete icon on conversation |
| **Toggle Sidebar** | Click collapse/expand arrow       |

### Conversation List

The sidebar shows:

- Conversation preview (first message)
- Timestamp
- Mode used (Work/General icon)

---

## Team Channels

### Creating a Team Channel

1. Click **+ New Channel** in the sidebar
1. Enter channel name and description
1. Choose visibility (public/private)
1. Click **Create**

### Channel Sidebar

| Section      | Contents                         |
| ------------ | -------------------------------- |
| **LLM**      | AI assistant conversations       |
| **Team**     | Team channels you're a member of |
| **Projects** | Project-linked channels          |
| **Direct**   | Private messages                 |

### Managing Members

| Action          | How                                  |
| --------------- | ------------------------------------ |
| **Invite**      | Click channel settings → Add Members |
| **Remove**      | Click member → Remove from channel   |
| **Change Role** | Click member → Change role           |

### Member Roles

| Role       | Permissions                      |
| ---------- | -------------------------------- |
| **Owner**  | Full control, can delete channel |
| **Admin**  | Manage members, edit settings    |
| **Member** | Send messages, share files       |

---

## Context Channels

### Project Channels

When you create a project, a chat channel is automatically created:

- **Auto-sync**: Project members become channel members
- **Access**: View from Project detail → Chat tab
- **Files**: Shared files appear in project files

See [Projects](../CRM/Projects.md) for project setup and membership.

### Lead Channels

Chat about specific leads with your team:

1. Open a lead/record detail
1. Click **Chat** tab
1. Channel created on first message

See [Records Management](../CRM/Records%20Management.md) for record details.

---

## File Sharing

### Uploading Files

1. Click **📎** attachment icon
1. Select file(s) to upload
1. Add optional message
1. Click **Send**

### File Integration

- Files uploaded in **Lead channels** → appear in Lead files
- Files uploaded in **Project channels** → appear in Project files
- Download files by clicking them in chat

---

## Real-time Features

### WebSocket Updates

- Messages appear instantly
- Typing indicators
- Online/offline status
- Unread message counts

### Notifications

- Badge counts on unread channels
- Desktop notifications (if enabled)
- Mute channels you don't want alerts from

---

## Work Mode Capabilities

### Data Queries (Coming Soon)

Ask questions about your records:

- "Show me high-quality leads from last week"
- "How many records have been analyzed?"
- "List companies in Birmingham with websites"

### Action Execution (Coming Soon)

Request actions through chat:

- "Send these leads to the pipeline"
- "Start crawling the new records"
- "Export all contacts with emails to CSV"

### Context Awareness

Work mode understands:

- Current page you're viewing
- Selected records (if any)
- Recent activity

---

## LLM Provider

Chat uses your configured LLM providers:

1. **CLI Bridge** (Free) - Gemini/Claude via CLI tools
1. **Ollama** (Free) - Local models like Llama
1. **API Providers** (Paid) - OpenAI, Anthropic, Google AI

Provider selection follows the fallback chain configured in Settings.

See [LLM Providers](../Settings/LLM%20Providers.md) for setup.

---

## Tips for Effective Chat

### Work Mode Tips

1. **Be specific** - "records in London" beats "UK records"
1. **Use field names** - "records with high lead_quality"
1. **Ask for counts first** - Before requesting full lists
1. **Specify timeframes** - "this week", "last month"

### General Mode Tips

1. **Provide context** - "I'm reaching out to accountants..."
1. **Ask for alternatives** - "What are other ways to..."
1. **Request formats** - "Give me a bullet-point list"
1. **Iterate** - "Make it more formal" / "Shorter please"

---

## Limitations

### Current Limitations

| Limitation             | Status      |
| ---------------------- | ----------- |
| Real-time data queries | Coming soon |
| Action execution       | Coming soon |
| Multi-modal (images)   | Planned     |
| Voice input            | Planned     |

### Rate Limits

Chat requests are rate-limited based on your LLM provider:

- 60 requests/minute per provider
- Automatic fallback to alternate providers

---

## Troubleshooting

### No Response

- Check LLM provider configuration in Settings
- Verify internet connection (for API providers)
- Check that CLI Bridge or Ollama is running

### Slow Responses

- CLI Bridge may take 30-60 seconds
- Consider using API providers for faster responses
- Check worker status in Jobs page (see [Jobs Monitor](Jobs%20Monitor.md))

### Incorrect Responses

- Rephrase your question
- Provide more context
- Try switching to a different mode
