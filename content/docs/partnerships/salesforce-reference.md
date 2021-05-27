---
title: "Salesforce Technical Reference"
description: "This page is updated with the technical documentation concerning Reseller and Affiliate management in Salesforce."
lead: "A running list of Frequently Asked Questions about the Partnerships program."
date: 2020-11-12T15:22:20+01:00
lastmod: 2020-11-12T15:22:20+01:00
draft: false
images: []
menu: 
  docs:
    parent: "partnerships"
weight: 630
toc: true
---

# Affiliates

This process makes use of a little-known object called Partner which stores the relationship and runs the reporting behind this process. [Review the object reference for the Partner object here before getting too deep into this reference guide.](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_partner.htm)

## Lead

{{< alert icon="⚠️" text="Start by reviewing the Reseller and Affiliate opportunities process documentation. This page will help guide some of the under-the-hood processes to the diagram being updated there.</a>." >}}

### Field Configuration
Affiliate tracking uses the following custom fields:
- [Related_Partner__c](https://cunning-raccoon-hisclg-dev-ed.lightning.force.com/lightning/setup/ObjectManager/Lead/FieldsAndRelationships/00N5e00000D7Q2F/view)
- [Partner_Agent__c](https://cunning-raccoon-hisclg-dev-ed.lightning.force.com/lightning/setup/ObjectManager/Lead/FieldsAndRelationships/00N5e00000D7fwC/view)
- [Related_Partner_ID_Text__c](https://cunning-raccoon-hisclg-dev-ed.lightning.force.com/lightning/setup/ObjectManager/Lead/FieldsAndRelationships/00N5e00000D7iHN/view)

| Field Name              | Usage                                                                                                                                                                        |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Related_Partner__c      | Lookup(Account) storing the Affiliate Partner                                                                                                                                |
| Partner_Agent__c        | Lookup(Contact) storing the Contact at Affiliate Partner account that referred Lead                                                                                          |
| Related_Partner_ID_Text | Required for Web-to-Lead configuration which cannot pass directly to the Related_Partner__c field. This is copied into Related_Partner__c by 2-Lead Modified Process Builder |

### Process Automation

Affiliate automation is centralized in the Account, Opportunity, and Lead PB starting at Version 1.3. [Jump to Process Builder](https://cunning-raccoon-hisclg-dev-ed.lightning.force.com/lightning/setup/ProcessAutomation/home)

Affiliate automation adds **1 new visual flow: Opportunity- Opportunity is Created with Related Partner**. [Jump to the flow](https://cunning-raccoon-hisclg-dev-ed.lightning.force.com/builder_platform_interaction/flowBuilder.app?flowId=3015e000000gIFFAA2)

{{< mermaid align="left" theme="neutral" >}}
graph TD
   id1[Start: Record Triggered Flow - Opportunity] --> id2[Create Partner Relationship Record] --> id3[Create Partner Agent<br>as Opportunity Contact Role]
{{< /mermaid >}}


**Description**:
This is a simple flow that runs when an Opportunity is created and **Related_Partner__c != null**. This flow can be modified to add additional functionality called from flow during Partner-related opportunity creation. 

Currently, it takes two main actions:
- Create Partner Relationship: This creates a new Partner record with a Lookup to both the current Opportunity and the Partner stored in Related_Partner__c. Depending on the type, it creates either an Affiliate or a Reseller type.
- Create Opportunity Contact Role for Partner_Agent__c: This adds the Partner Agent as an Opportunity contact role. The role is hard-coded to Partner Agent but can be modified afterwards.