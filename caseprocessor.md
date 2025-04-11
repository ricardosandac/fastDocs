---
layout: default
title: CaseProcessor
nav_order: 9
---

# CaseProcessor

The `CaseProcessor` class handles operations related to case records, such as updating statuses and assigning cases.

## Methods

### `updateCaseStatus`
Updates the status of a case.

```apex
public static void updateCaseStatus(Id caseId, String status) {
    Case caseRecord = [SELECT Id, Status FROM Case WHERE Id = :caseId];
    caseRecord.Status = status;
    update caseRecord;
}
```

### `assignCaseToUser`
Assigns a case to a specific user.

```apex
public static void assignCaseToUser(Id caseId, Id userId) {
    Case caseRecord = [SELECT Id, OwnerId FROM Case WHERE Id = :caseId];
    caseRecord.OwnerId = userId;
    update caseRecord;
}
```

### Features
- Streamlines case management.
- Provides methods for updating and assigning cases.

## Usage Example

```apex
CaseProcessor.updateCaseStatus('500XXXXXXXXXXXXXXX', 'Closed');
CaseProcessor.assignCaseToUser('500XXXXXXXXXXXXXXX', '005XXXXXXXXXXXXXXX');
```
