---
layout: default
title: FieldAuditor
nav_order: 21
---

# FieldAuditor

The `FieldAuditor` class tracks changes to specific fields.

## Methods

### `auditFieldChange`
Logs changes to a specified field.

```apex
public static void auditFieldChange(SObject record, String fieldName) {
    // Logic to log field changes
}
```

### Features
- Tracks field-level changes.
- Provides audit trail for compliance.

## Usage Example

```apex
FieldAuditor.auditFieldChange(accountRecord, 'Name');
```
