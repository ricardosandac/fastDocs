---
layout: default
title: Code Examples
nav_order: 4
---

# Code Examples

Below are some examples of Apex code from the repository:

## Example 1: Trigger Handler
```apex
// filepath: src/triggers/ExampleTrigger.trigger
trigger ExampleTrigger on Account (before insert, before update) {
    TriggerHandler.handleTrigger(Trigger.new, Trigger.oldMap);
}
```

## Example 2: Utility Class
```apex
// filepath: src/classes/UtilityClass.cls
public class UtilityClass {
    public static String formatString(String input) {
        return input.trim().toUpperCase();
    }
}
```
