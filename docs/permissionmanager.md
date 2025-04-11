---
layout: default
title: PermissionManager
nav_order: 22
---

# PermissionManager

The `PermissionManager` class manages user permissions.

## Methods

### `assignPermissionSet`
Assigns a permission set to a user.

```apex
public static void assignPermissionSet(Id userId, String permissionSetName) {
    // Logic to assign permission set
}
```

### Features
- Simplifies permission management.
- Supports dynamic assignment.

## Usage Example

```apex
PermissionManager.assignPermissionSet('005XXXXXXXXXXXXXXX', 'CustomPermissionSet');
```
