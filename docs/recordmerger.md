---
layout: default
title: RecordMerger
nav_order: 20
---

# RecordMerger

The `RecordMerger` class merges duplicate records.

## Methods

### `mergeRecords`
Merges two records of the same type.

```apex
public static void mergeRecords(SObject masterRecord, SObject duplicateRecord) {
    // Logic to merge records
}
```

### Features
- Ensures data consistency.
- Simplifies duplicate management.

## Usage Example

```apex
RecordMerger.mergeRecords(masterAccount, duplicateAccount);
```
