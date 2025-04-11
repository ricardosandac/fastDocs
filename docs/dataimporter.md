---
layout: default
title: DataImporter
nav_order: 16
---

# DataImporter

The `DataImporter` class handles bulk data imports.

## Methods

### `importData`
Imports data from a CSV file.

```apex
public static void importData(String csvContent) {
    // Logic to parse and insert data
}
```

### Features
- Supports bulk data operations.
- Simplifies data import processes.

## Usage Example

```apex
String csvContent = 'Name,Email\nJohn Doe,john.doe@example.com';
DataImporter.importData(csvContent);
```
