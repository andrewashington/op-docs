---
title: "Reseller Process"
description: "This page diagrams the process when a Reseller submits a new deal to OpDocs."
lead: "This page describes both the process for adding new Resellers to our partner program, and what happens to Opportunities that are created from Reseller data."
date: 2020-10-06T08:49:31+00:00
lastmod: 2020-10-06T08:49:31+00:00
draft: false
images: []
menu:
  docs:
    parent: "partnerships"
weight: 610
toc: true
---

## Summary

This process page describes the current Reseller process. 

For more strategic and definitional detail, visit [the Partnership Program Summary](../how-to-update)

## Creating a New Reseller

### Diagram
{{< mermaid align="left" theme="neutral" >}}
graph TD
  id1[New Partner Inquiry]  -- Qualified --> id2[Create Opportunity of Type = New Reseller]
  id2 --> id3[Send Reseller Agreement]
  id3 -- Reseller Agreement Signed --> id4[Closed Won]
  id4 --> id5[Reseller onboarding packet delivered]
{{< /mermaid >}}

### Written Process
1. Partnerships team receives a new Partnership inquiry.
2. Partnerships team creates a new Opportunity and sets Opportunity Type to 'New Reseller' and owns the closing process.
3. Owner sends Reseller Primary Contact a Reseller Agreement using DocuSign.
4. Owner marks Opportunity as Closed Won when Reseller signs agreement.
5. Salesforce automatically sends Reseller Information packet including:
   1. Reseller ID
   2. Reseller form embed code
   3. Welcome material and collateral
6. Reseller is onboarded and deals will start contributing to Partnerships KPI Dashboard.

## Closing a Reseller Opportunity
{{< alert icon="📑" text="Unlike closing new Partners, Reseller deal registration is largely automated. This process is for reference purposes.</a>" >}}

### Diagram
{{< mermaid align="left" theme="dark" >}}
graph TD
  id1[Reseller submits Deal Registration Form]  -- Salesforce Sync --> id2[Opportunity is created of <br>Type = New Customer - Reseller]
  id2 -- Opportunity is assigned to 'Pending Deal Registration Queue' --> id3[Sales Operations reviews <br> incoming opportunity registration]
  id3 -- Deal approved --> id4[Opportunity <br>is changed to Closed Won]
  id3 -- Deal rejected --> id5[Opportunity<br> stage is changed to Rejected]
  id5 -- Deal assigned to Partnerships --> id6[Partnership works directly with Reseller to resolve]
  id6 --Deal is ready for resubmission --> id3
  id4 --> id7[Onboarding case is created]
{{< /mermaid >}}

### Written process
1. Reseller submits Deal Registration Form from their personalized welcome packet.
2. A new Opportunity is created with customer information with Type = 'New Customer - Reseller'. 
3. Opportunity owner is changed to Pending Deal Registration Queue
4. Sales Operations reviews deal criteria for accurate information, pricing, products, and adds required new customer data.
5. Opportunity is changed to Closed Won.

If Deal Registration form is inaccurate, incomplete, or otherwise prevents creating the new customer:
1. Sales Operations reassigns Opportunity to Partnership Team
2. Opportunity Stage is changed to 'Rejected' and Reseller Rejected Reason is updated.
3. Sales Operations updates Opportunity Notes and Chatter to reflect issues with processing the customer.

When Partnerships has resolved Rejection reasons:
1. Partnership team reassigns Opportunity to Pending Deal Registration Queue.
2. Sales Operations is notified to reprocess opportunity.

## Related Resources
- [Deal Registration Sample Form](.deal.registration.form.sample)
- [Pending Deal Registration Queue](.deal.registration.queue)
- [Rejected Reseller Opportunities](.deals.rejected)
- [Closed Won Reseller Opportunities](.deals.closed.won)

