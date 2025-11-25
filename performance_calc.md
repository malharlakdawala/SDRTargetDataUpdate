# Performance Calculation Logic

## Metrics Tracked

| Metric | Source | Target |
|--------|--------|--------|
| Calls Made | Close CRM Activity | 50/day |
| Emails Sent | Close CRM Activity | 30/day |
| Meetings Booked | Close CRM Activity | 3/day |
| Pipeline Generated | Close CRM Opportunities | $10k/week |

## Score Formula

```
daily_score = (calls/50 * 0.3) + (emails/30 * 0.2) + (meetings/3 * 0.3) + (pipeline/10000 * 0.2)
```

Score is capped at 1.0 (100%). SDRs scoring above 0.8 consistently are flagged as top performers.
