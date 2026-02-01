# Jobs Monitor

The Jobs Monitor lets you track and manage all background processing tasks in Ettutu V2, including
crawling, analysis, and export operations.

<!-- Screenshot: Jobs page showing job list and system status -->

---

## Overview

Background jobs handle long-running tasks:

- Website crawling (per record)
- AI analysis (per record)
- Bulk exports
- Data imports

---

## Accessing Jobs Monitor

Click **Jobs** in the sidebar navigation.

---

## Jobs Dashboard

### System Status Panel

Shows overall system health:

| Indicator   | Description                          |
| ----------- | ------------------------------------ |
| **Redis**   | Job queue connection status          |
| **Workers** | Worker pool status (running/stopped) |
| **API**     | Backend API health                   |

<!-- Screenshot: System status panel with all indicators green -->

### Active Jobs Counter

Shows count of currently processing jobs.

---

## Jobs List

### Job Entry Fields

| Field        | Description                       |
| ------------ | --------------------------------- |
| **ID**       | Unique job identifier             |
| **Type**     | Job type (crawl, analyze, export) |
| **Record**   | Associated record name            |
| **Status**   | Current status                    |
| **Progress** | Completion percentage             |
| **Started**  | When job began                    |
| **Duration** | Time elapsed                      |

<!-- Screenshot: Jobs list with various job types -->

### Job Statuses

| Status        | Meaning                     | Color  |
| ------------- | --------------------------- | ------ |
| **Queued**    | Waiting to start            | Gray   |
| **Active**    | Currently processing        | Blue   |
| **Complete**  | Finished successfully       | Green  |
| **Failed**    | Error occurred              | Red    |
| **Cancelled** | User cancelled              | Orange |
| **Retrying**  | Automatic retry in progress | Yellow |

---

## Job Types

### Crawl Jobs

Website crawling for data extraction:

```text
Type: crawl
Plugin: fast_crawler / deep_crawler / llm_crawler
Duration: 5-120 seconds per record
```

### Analyze Jobs

AI analysis of crawled content:

```text
Type: analyze
Plugin: lead_analyzer
Duration: 10-60 seconds per record
```

### Export Jobs

Data export operations:

```text
Type: export
Format: CSV / JSON / Excel
Duration: Varies by record count
```

---

## Job Actions

### Cancel Job

Stop a running job:

1. Find job in list
1. Click **Cancel** button
1. Confirm cancellation

Note: Partially completed work may be saved.

### Retry Job

Re-run a failed job:

1. Find failed job
1. Click **Retry** button
1. Job returns to queue

### View Job Details

Click a job row to see:

- Full error messages (if failed)
- Processing logs
- Resource usage
- Associated record link

---

## Filtering Jobs

### By Status

| Filter       | Shows             |
| ------------ | ----------------- |
| **All**      | Every job         |
| **Active**   | Currently running |
| **Queued**   | Waiting to start  |
| **Failed**   | Error state       |
| **Complete** | Finished          |

### By Type

| Filter        | Shows            |
| ------------- | ---------------- |
| **All Types** | All job types    |
| **Crawl**     | Website crawling |
| **Analyze**   | AI analysis      |
| **Export**    | Data exports     |

---

## Real-Time Logs

### Live Streaming

During active jobs:

- Logs stream in real-time via SSE
- Progress updates automatically
- No page refresh needed

### Log Content

```text
[14:32:01] Starting crawl for "Example Company"
[14:32:02] Fetching https://example.com
[14:32:05] Found 3 pages to process
[14:32:12] Extracted 2 email addresses
[14:32:15] Crawl complete
```

---

## Worker Management

### Restart Workers

If workers are stuck or unresponsive:

1. Click **Restart Workers** button
1. Confirm restart
1. Wait for workers to reconnect

<!-- Screenshot: Restart workers confirmation dialog -->

### Worker Pool

Default configuration:

- **10 concurrent workers**
- Jobs distributed automatically
- Priority queue for urgent tasks

---

## Crawl Progress Modal

When bulk crawling from Records or Searches:

- Modal shows overall progress
- Individual record status
- Estimated time remaining
- Cancel option

<!-- Screenshot: Crawl progress modal during bulk operation -->

---

## Job Queue System

### How It Works

```text
1. User triggers action (crawl, analyze)
   ↓
2. Jobs added to Redis queue
   ↓
3. Workers pull jobs
   ↓
4. Processing in background
   ↓
5. Status updates saved to database
   ↓
6. UI polls for updates
```

### Queue Priority

Jobs processed in order:

1. Retry attempts (highest)
1. Standard jobs (FIFO)
1. Bulk operations (lowest)

---

## Monitoring Best Practices

### Regular Checks

- Monitor for stuck jobs (active too long)
- Review failed jobs for patterns
- Check worker status after deployments

### Troubleshooting Stuck Jobs

1. Check system status panel
1. Verify Redis connection
1. Restart workers if needed
1. Cancel and retry individual jobs

---

## Configuration

### Environment Settings

| Setting                | Default | Description           |
| ---------------------- | ------- | --------------------- |
| `WORKER_CONCURRENCY`   | 10      | Max concurrent jobs   |
| `JOB_TIMEOUT`          | 600s    | Max job duration      |
| `JOB_MAX_RETRIES`      | 3       | Auto-retry attempts   |
| `WORKER_POLL_INTERVAL` | 1s      | Queue check frequency |

Configure in Settings or `.env` file.

---

## Troubleshooting

### Workers Not Starting

- Check Redis connection
- Verify Docker container is running
- Check worker logs for errors

### Jobs Failing Repeatedly

- Check error details in job view
- Verify external API credentials
- Check target website accessibility

### Slow Processing

- Review concurrent job count
- Check system resources
- Consider reducing batch sizes
