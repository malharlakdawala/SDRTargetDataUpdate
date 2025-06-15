# SDR Target Data Update

n8n automation that syncs SDR daily target and performance data from Close CRM to Airtable for real-time dashboards and performance tracking.

## Workflow

<img width="1271" height="591" alt="SDR Target Data Workflow" src="https://github.com/user-attachments/assets/4d5a34af-4b0f-42cb-accc-1b518462505c" />

## Overview

This workflow runs on a schedule and:
1. Fetches daily call/email/meeting metrics per SDR from Close CRM
2. Calculates performance against daily targets
3. Pushes structured data to Airtable for dashboards and reporting
4. Sends Slack alerts for SDRs below target thresholds

## Setup

1. Import `SDR Targets Data from Close to Airtable.blueprint.json` into your n8n instance
2. Configure Close CRM API credentials
3. Configure Airtable API credentials
4. Set the cron schedule (default: daily at 9 AM IST)

## Configuration

| Variable | Description |
|----------|-------------|
| `CLOSE_API_KEY` | Close CRM API key |
| `AIRTABLE_API_KEY` | Airtable personal access token |
| `AIRTABLE_BASE_ID` | Target Airtable base ID |
| `SLACK_WEBHOOK_URL` | Slack webhook for notifications |
| `SCHEDULE` | Cron expression (default: `0 9 * * 1-5`) |

## Metrics Tracked

| Metric | Source | Daily Target |
|--------|--------|-------------|
| Calls Made | Close CRM Activity | 50 |
| Emails Sent | Close CRM Activity | 30 |
| Meetings Booked | Close CRM Activity | 3 |
| Pipeline Generated | Close CRM Opportunities | $10k/week |

## Error Handling

- Retries failed API calls up to 3 times with exponential backoff
- Sends Slack notification on persistent failures
- Logs all sync operations for audit trail
