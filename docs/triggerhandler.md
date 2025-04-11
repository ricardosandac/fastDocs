---
layout: default
title: TriggerHandler
nav_order: 4
---

# TriggerHandler

The `TriggerHandler` class is responsible for managing trigger logic in a structured and reusable way. It ensures that business logic is separated from the trigger itself.

## Methods

### `handleTrigger`
Handles the execution of trigger logic.

```apex
public static void handleTrigger(List<SObject> newRecords, Map<Id, SObject> oldMap) {
    // Logic to process trigger events
}
```

### Features
- Supports multiple trigger events (e.g., `before insert`, `after update`).
- Promotes separation of concerns by delegating logic to helper methods.

## Usage Example

```apex
trigger AccountTrigger on Account (before insert, after update) {
    TriggerHandler.handleTrigger(Trigger.new, Trigger.oldMap);
}
```
