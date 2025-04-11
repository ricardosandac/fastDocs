---
layout: default
title: EmailService
nav_order: 11
---

# EmailService

The `EmailService` class provides methods for sending emails.

## Methods

### `sendEmail`
Sends an email to a specified recipient.

```apex
public static void sendEmail(String recipient, String subject, String body) {
    Messaging.SingleEmailMessage email = new Messaging.SingleEmailMessage();
    email.setToAddresses(new String[] { recipient });
    email.setSubject(subject);
    email.setPlainTextBody(body);
    Messaging.sendEmail(new Messaging.SingleEmailMessage[] { email });
}
```

### Features
- Simplifies email sending.
- Supports plain text emails.

## Usage Example

```apex
EmailService.sendEmail('example@example.com', 'Subject', 'Email body content');
```
