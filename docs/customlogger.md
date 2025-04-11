---
layout: default
title: CustomLogger
nav_order: 14
---

# CustomLogger

The `CustomLogger` class provides logging utilities for debugging and monitoring.

## Methods

### `log`
Logs a message with a specified log level.

```apex
public static void log(String level, String message) {
    System.debug('[' + level + '] ' + message);
}
```

### Features
- Supports different log levels (e.g., INFO, ERROR).
- Simplifies debugging.

## Usage Example

```apex
CustomLogger.log('INFO', 'This is an informational message.');
```
