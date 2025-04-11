---
layout: default
title: LeadConverter
nav_order: 10
---

# LeadConverter

The `LeadConverter` class handles the conversion of leads into accounts, contacts, and opportunities.

## Methods

### `convertLead`
Converts a lead into an account, contact, and optionally an opportunity.

```apex
public static void convertLead(Id leadId, Boolean createOpportunity) {
    LeadConvert lc = new LeadConvert();
    lc.setLeadId(leadId);
    lc.setDoNotCreateOpportunity(!createOpportunity);
    Database.LeadConvertResult result = Database.convertLead(lc);
    if (!result.isSuccess()) {
        throw new CustomException('Lead conversion failed: ' + result.getErrors());
    }
}
```

### Features
- Automates lead conversion.
- Provides error handling for failed conversions.

## Usage Example

```apex
LeadConverter.convertLead('00QXXXXXXXXXXXXXXX', true);
```
