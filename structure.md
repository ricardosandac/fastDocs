---
layout: default
title: Repository Structure
nav_order: 3
---

# Repository Structure

The repository is organized as follows:

```
apex-recipes/
├── src/
│   ├── classes/       # Apex classes
│   │   ├── TriggerHandler.cls  # Handles trigger logic
│   │   ├── UtilityClass.cls    # Provides utility methods
│   │   └── ...other classes...
│   ├── triggers/      # Apex triggers
│   └── tests/         # Test classes
├── docs/              # Documentation
└── README.md          # Project overview
```

Each folder contains specific components to help you navigate and understand the repository.

## Classes
- [TriggerHandler](triggerhandler.md): Handles trigger logic and ensures separation of concerns.
- [UtilityClass](utilityclass.md): Provides reusable utility methods for string manipulation and more.
- ...other classes...
