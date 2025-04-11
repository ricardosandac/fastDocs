---
layout: default
title: QueueProcessor
nav_order: 19
---

# QueueProcessor

The `QueueProcessor` class processes records in a queue.

## Methods

### `processQueue`
Processes records from a specified queue.

```apex
public static void processQueue(String queueName) {
    // Logic to process queue records
}
```

### Features
- Supports custom queue names.
- Automates record processing.

## Usage Example

```apex
QueueProcessor.processQueue('MyQueue');
```
