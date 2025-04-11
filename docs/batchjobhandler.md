---
layout: default
title: BatchJobHandler
nav_order: 12
---

# BatchJobHandler

The `BatchJobHandler` class manages batch jobs for processing large datasets asynchronously.

## Methods

### `executeBatch`
Executes a batch job with the specified scope size.

```apex
public static void executeBatch(Database.Batchable<SObject> batchJob, Integer scopeSize) {
    Database.executeBatch(batchJob, scopeSize);
}
```

### Features
- Simplifies batch job execution.
- Supports custom scope sizes for processing.

## Usage Example

```apex
BatchJobHandler.executeBatch(new MyBatchClass(), 200);
```
