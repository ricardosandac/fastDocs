---
layout: default
title: UtilityClass
nav_order: 5
---

# UtilityClass

The `UtilityClass` provides reusable utility methods that can be used across the application.

## Methods

### `formatString`
Formats a string by trimming whitespace and converting it to uppercase.

```apex
public static String formatString(String input) {
    return input.trim().toUpperCase();
}
```

### Features
- Simplifies string manipulation.
- Ensures consistent formatting across the application.

## Usage Example

```apex
String formatted = UtilityClass.formatString('  example ');
System.debug(formatted); // Outputs: EXAMPLE
```
