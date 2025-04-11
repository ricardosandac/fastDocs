---
layout: default
title: OpportunityManager
nav_order: 8
---

# OpportunityManager

The `OpportunityManager` class is responsible for managing operations related to opportunities, such as creating, updating, and retrieving records.

## Methods

### `createOpportunity`
Creates a new opportunity record.

```apex
public static Opportunity createOpportunity(String name, Id accountId) {
    Opportunity opp = new Opportunity(Name = name, AccountId = accountId, StageName = 'Prospecting', CloseDate = Date.today().addDays(30));
    insert opp;
    return opp;
}
```

### `getOpportunitiesByAccount`
Retrieves opportunities associated with a specific account.

```apex
public static List<Opportunity> getOpportunitiesByAccount(Id accountId) {
    return [SELECT Id, Name, StageName, CloseDate FROM Opportunity WHERE AccountId = :accountId];
}
```

### Features
- Simplifies opportunity management.
- Provides reusable methods for common operations.

## Usage Example

```apex
Opportunity newOpp = OpportunityManager.createOpportunity('New Deal', '001XXXXXXXXXXXXXXX');
List<Opportunity> opportunities = OpportunityManager.getOpportunitiesByAccount('001XXXXXXXXXXXXXXX');
System.debug(opportunities);
```
