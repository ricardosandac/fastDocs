---
layout: default
title: ReportGenerator
nav_order: 17
---

# ReportGenerator

The `ReportGenerator` class generates reports based on Salesforce data.

## Methods

### `generateReport`
Generates a report for a given object.

```apex
public static String generateReport(String objectName) {
    // Logic to generate report
    return 'Report content';
}
```

### Features
- Customizable report generation.
- Supports multiple objects.

## Usage Example

```apex
String report = ReportGenerator.generateReport('Account');
System.debug(report);
```
