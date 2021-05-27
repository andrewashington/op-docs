---
title: "Shared Partner Forms"
description: "This page contains information about the Partner Lead Form for affiliates, and Partner deal registration form for resellers"
lead: "A sample Partner Lead form with a description of how it works."
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "partnerships"
weight: 130
toc: true
---

## What is this?
To process leads from our Affiliates and Reseller Partners, we share an embeddable lead form with them that inserts their Account ID from Salesforce to tie their shared data back to the partner. 

This page stores an example of that web-to-lead script and parameters that are used. 

## Sample Script

**This form should only be used in authorized environments, like a secured company intranet portal, and shouldn't be made available on the public-facing web since it creates a spam risk.** 

```html
<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: Please add the following <META> element to your page <HEAD>.      -->
<!--  If necessary, please modify the charset parameter to specify the        -->
<!--  character set of your HTML page.                                        -->
<!--  ----------------------------------------------------------------------  -->

<META HTTP-EQUIV="Content-type" CONTENT="text/html; charset=UTF-8">

<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: Please add the following <FORM> element to your page.             -->
<!--  ----------------------------------------------------------------------  -->

<form action="https://webto.salesforce.com/servlet/servlet.WebToLead?encoding=UTF-8" method="POST">

<input type=hidden name="oid" value="00D5e000001Acue">
<input type=hidden name="retURL" value="http://www.opdocs.com/thank-you">

<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: These fields are optional debugging elements. Please uncomment    -->
<!--  these lines if you wish to test in debug mode.                          -->
<!--  <input type="hidden" name="debug" value=1>                              -->
<!--  <input type="hidden" name="debugEmail"                                  -->
<!--  value="andre.washington@divvypay.com">                                  -->
<!--  ----------------------------------------------------------------------  -->

<label for="first_name">First Name</label><input  id="first_name" maxlength="40" name="first_name" size="20" type="text" /><br>

<label for="last_name">Last Name</label><input  id="last_name" maxlength="80" name="last_name" size="20" type="text" /><br>

<label for="email">Email</label><input  id="email" maxlength="80" name="email" size="20" type="text" /><br>

<label for="company">Company</label><input  id="company" maxlength="40" name="company" size="20" type="text" /><br>

<input type="submit" name="submit">

<input type="hidden" value="##PARTNER ACCOUNT ID IS INSERTED HERE##">

</form>
```

## Technical Notes

This script can be embedded anywhere and used to input leads to our Salesforce. 

{{< alert icon="⚠️" text="Major headache on this. Using default Web-to-Lead functionality, you **CANNOT* populate a Lookup field. As a result, this form must post to a text field which is then copied into the lookup on creation in Salesforce.</a>." >}}


### **Hidden Form Field Variables**:
- **Partner_Account__c** is passed from this form and can be seen as a hidden input type field in the sample script. 
- - This field should be set to the related Partner Account ID before sharing with a Partner.
- **Partner_Agent__c**: This can be used to pass a contact ID into the form, such as form codes that are associated with specific contacts at a Partner account.

### Create Test Lead

You can use this ugly embedded form to test this process. This uses the default Partner embed script with hard-coded values that point to OpDocs. This can be used sparingly to model the process without creating reporting issues.


<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: Please add the following <META> element to your page <HEAD>.      -->
<!--  If necessary, please modify the charset parameter to specify the        -->
<!--  character set of your HTML page.                                        -->
<!--  ----------------------------------------------------------------------  -->

<META HTTP-EQUIV="Content-type" CONTENT="text/html; charset=UTF-8">

<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: Please add the following <FORM> element to your page.             -->
<!--  ----------------------------------------------------------------------  -->

<form action="https://webto.salesforce.com/servlet/servlet.WebToLead?encoding=UTF-8" method="POST">

<input type=hidden name="oid" value="00D5e000001Acue">
<input type=hidden name="retURL" value="www.salesforce.com">

<!--  ----------------------------------------------------------------------  -->
<!--  NOTE: These fields are optional debugging elements. Please uncomment    -->
<!--  these lines if you wish to test in debug mode.                          -->
<!--  <input type="hidden" name="debug" value=1>                              -->
<!--  <input type="hidden" name="debugEmail"                                  -->
<!--  value="andre.washington@divvypay.com">                                  -->
<!--  ----------------------------------------------------------------------  -->

<label for="first_name">First Name</label><input  id="first_name" maxlength="40" name="first_name" size="20" type="text" /><br>

<label for="last_name">Last Name</label><input  id="last_name" maxlength="80" name="last_name" size="20" type="text" /><br>

<label for="email">Email</label><input  id="email" maxlength="80" name="email" size="20" type="text" /><br>

<label for="company">Company</label><input  id="company" maxlength="40" name="company" size="20" type="text" /><br>

<input type="hidden" name="00N5e00000D7iHN" id="00N5e00000D7iHN" value="0015e000006LTveAAG" /><br>

<input type="hidden" name="lead_source" id="lead_source" value="Web" /><br>

<input type="submit" name="submit">

</form>


## Partner Deal Registration Form

Deal registration for Resellers works much the same as affiliates, except that it collects more data and kicks off a process in Salesforce to automatically convert the lead and assign for Sales Operations review.

For more information on the Reseller process flow, visit [the Reseller and Affiliate deal process](https://developer.salesforce.com/docs/atlas.en-us.object_reference.meta/object_reference/sforce_api_objects_partner.htm)