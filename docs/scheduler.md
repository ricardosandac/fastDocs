---
layout: default
title: Scheduler
nav_order: 13
---

# Scheduler

The `Scheduler` class schedules Apex jobs to run at specific times.

## Methods

### `scheduleJob`
Schedules a job with a given cron expression.

```apex
public static void scheduleJob(String jobName, String cronExpression, Schedulable schedulableClass) {
    System.schedule(jobName, cronExpression, schedulableClass);
}
```

### Features
- Supports custom cron expressions.
- Simplifies job scheduling.

## Usage Example

```apex
Scheduler.scheduleJob('Daily Job', '0 0 12 * * ?', new MySchedulableClass());
```
