---
layout: default
title: NotificationService
nav_order: 18
---

# NotificationService

The `NotificationService` class handles sending notifications to users.

## Methods

### `sendNotification`
Sends a notification to a user.

```apex
public static void sendNotification(Id userId, String message) {
    // Logic to send notification
}
```

### Features
- Supports user-specific notifications.
- Simplifies notification management.

## Usage Example

```apex
NotificationService.sendNotification('005XXXXXXXXXXXXXXX', 'You have a new task.');
```
