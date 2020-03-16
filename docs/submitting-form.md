---
title: Submitting form
date: 2020-03-13
slug: submit-form

---
## Basic steps

The RF-1189 form needs to be attached to an existing RF-1030 form. The basic steps to submit a full form are as follows:

1. Find out which RF-1030 form does the user wish to attach the RF-1189 form to. In the app, this will be either the current or the **last tax year**.
2. Authenticate the user.
3. Find the ReporteeElementID for the form they wish to attach RF-1189 to.
4. Generate the RF-1189 form
5. Submit a UpdateFormDataBasic request with the correct parameters

## Form to use

Each year, say 2020, requires the form from the previous year to be submitted. But it is possible for users to submit from the year before that too.

For example, in 2020 the application RF-1030 form will be for 2019 (current year submission) and 2018 (previous year)

[See Forms section](/forms-2020)

## Authenticate the user

Use the [GetAuthenticationChallenge](/get-authentication-challenge) end point to authenticate the user. The AltinnPin method will result in sending a SMS pin to the user which they need to enter in the app; this will be used for retrieving RF-1030 form and sending in RF-1189 form.

1. Ask the user to input their UserSSN and UserPassword (AltinnPin auth method)
2. Send the SOAP envelope to the server
3. Check that the response field a:Status is OK (any other output or not found is not)
4. 

## Find the ReporteeElementID

1. Get the systemUserName, systemPassword, userSSN, userPassword and userPinCode (SMS pin) from users. The UserSSN and userPassword were obtained in the previous steps. We may save this temporarily in the server (till the time we are processing) but need to recheck if we need to delete this.
2. Find the tax year they wish to submit the form for. This will determine what year range to look for in Get Reportee Element endpoint.
3. Use the [GetReporteeElementListBasicV2](/get-reportee-element-list) end point to send a request with the above parameters
4. Check the response and make sure we have atleast one ReporteeElementBEV2
5. Look for the form id (a:ReporteeElementId) with the fields  
   ExternalServiceCode: 3348 or 3349 (Based on the type of RF-1030 form. We can look for either ones for now)  
   ServiceEditionVersion: 180141 or 180143 for 2019; 164387 or 164393 for 2018  
   Status: FillIn
6. Save the found ReporteeElementId for use in the next steps. Will also need the info from step 1

## Generate the RF-1189 form

TODO

## Submit

1. Get the systemUserName, systemPassword, userSSN, userPassword and userPinCode (SMS pin) from users. The UserSSN and userPassword were obtained in the previous steps. We may save this temporarily in the server (till the time we are processing) but need to recheck if we need to delete this.
2. Based on the UpdateFormDataBasic endpoint template and the user's selected form, fill in the DataFormatId, DataFormatVersion and ReporteeElementId. Note that the DataFormatVersion has to also be filled in the generated form's xml attribute spesifikasjonsnummer as well or we'll get an error.
3. Add the generated form in FormData xml field
4. Submit the envelope
5. Check the response status codes.  
   _For errors in request parameters besides form validation look at UpdateFormDataBasicResult->ReceiptStatusCode  
   _This should be 'OK'. Failed status is 'Rejected'  
   _For errors pertaining to form XML look at UpdateFormDataBasicResult->SubReceipts->ReceiptExternal->ReceiptStatusCode  
   _This should be OK. If validation failed this will be 'ValidationFailed'  
   Both _ReceiptStatusCode_ should be OK for a successful submission. Also, note there will be multiple _ReceiptStatusCode_ if multiple forms.

Notes:

* It take a while (up to 2-5 mins) for the form to appear in Altinn