---
title: "Affiliate Process"
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

This process page describes the current Affiliate process for both creating new Resellers in our system, and monitoring deals registered to us by our Resellers.

For more strategic and definitional detail, visit [the Partnership Program Summary](../how-to-update)

## Creating a New Affiliate Partner

### Diagram
{{< mermaid align="left" theme="neutral" >}}
graph TD
  id1[New Partner Inquiry]  -- Qualified --> id2[Create Opportunity of Type = New Affiliate]
  id2 --> id3[Send Affiliate Agreement]
  id3 -- Affiliate Agreement Signed --> id4[Closed Won]
  id4 --> id5[Affiliate onboarding packet delivered]
{{< /mermaid >}}

### Written Process
1. Partnerships team receives a new Partnership inquiry.
2. Partnerships team creates a new Opportunity and sets Opportunity Type to 'New Affiliate' and owns the closing process.
3. Owner sends Affiliate Primary Contact a Affiliate Agreement using DocuSign.
4. Owner marks Opportunity as Closed Won when Affiliate signs agreement.
5. Salesforce automatically sends Reseller Information packet including:
   1. Affiliate ID
   2. Affiliate form embed code
   3. Welcome material and collateral
6. Afiliate is onboarded and deals will start contributing to Partnerships KPI Dashboard.

## Working with Affiliate Leads
{{< alert icon="📑" text="tl;dr: Use the 'My Affiliate Leads' list view to find your leads that were sent to us by Affiliates.</a>" >}}

### Summary

Affiliates will share Lead data with us from their existing customers and audiences. It is our job to contact the Lead, set an appointment, convert to an Opportunity, and close the business. 

In essence, these leads are a very warm Inbound demo request that an Affiliate may have already qualified for us. The task of business development is to confirm the Affiliate relationship and qualifying information.

### Rejecting Affiliate Leads

If Affiliate Lead data is inaccurate, incomplete, or otherwise prevents contacting the prospect:
1. Change Lead Status to **Rejected**.
2. Change **Rejected Reason** to "Refer to Affiliate".
3. This will automatically queue the Partnerships team to review the Lead with Affiliate and update status.

When Partnerships has resolved Rejection reasons:
1. Partnership team to change Lead Status to **Need Sales Follow Up**.
2. This will automatically bring the Lead back into the Sales pipeline and queue for contact.


