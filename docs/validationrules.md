---
layout: default
title: ValidationRules
nav_order: 15
---

# ValidationRules

The `ValidationRules` class provides methods to validate business rules.

## Methods

### `validateEmail`
Validates if an email address is in the correct format.

```apex
public static Boolean validateEmail(String email) {
    return Pattern.matches('^[\\w.%+-]+@[\\w.-]+\\.[a-zA-Z]{2,}$', email);
}
```

### Features
- Ensures data integrity.
- Provides reusable validation logic.

## Usage Example

```apex
Boolean isValid = ValidationRules.validateEmail('example@example.com');
System.debug(isValid); // Outputs: true
```
