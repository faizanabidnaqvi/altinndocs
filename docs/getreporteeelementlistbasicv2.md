---
title: GetReporteeElementListBasicV2
date: 2020-03-13
slug: GetReporteeElementListBasicV2

---
This endpoint is used to find all the forms in the system.  In our scenario, we will use to find the RF-1030 form we wish to attach RF-1189 to. They can be filtered based on criteria as well.

Before sending this request, we need to find out the systemUserName and systemPassword from the user. This is set by the user in Altinn settings to let external systems access their profile.

systemUserName: System user name set by the users in their settings for external access

systemPassword: System password set by the users in their settings for external access

userSSN: Social security number (same as used for MINID Auth. TODO: Check other auth methods)

userPassword: Password (same as used for MINID Auth. TODO: Check other auth methods)

userPinCode: SMS received after authentication. This is for the AltinnPin method. We do need to check other methods as well.

authMethod: Authentication methods. At the moment, we are using AltinnPin only.

For searching,

FromDate: Start date to start the search from. The format is: 2019-01-01

Reportee: A user may have multiple accounts in Altinn. And therefore the Reportee might be different for other accounts. However, in our case for user's personal account this number is the same as SSN.

ToDate: End date for the search. The format is: 2020-03-16

Langauge,

languageID: We use 1033 for English. TODO: Find id for Norwegian is.

**Request Example**

    <soapenv:Envelope
      xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
      xmlns:ns="http://www.altinn.no/services/ServiceEngine/ReporteeElementList/2009/10"
      xmlns:ns1="http://schemas.altinn.no/services/Archive/ReporteeArchive/2009/10"
      xmlns:arr="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
      <soapenv:Header/>
      <soapenv:Body>
        <ns:GetReporteeElementListBasicV2>
          <ns:systemUserName>hauk_olaussen</ns:systemUserName>
          <ns:systemPassword>password01</ns:systemPassword>
          <ns:userSSN>30014500525</ns:userSSN>
          <ns:userPassword>password01</ns:userPassword>
          <ns:userPinCode>12345</ns:userPinCode>
          <ns:authMethod>AltinnPin</ns:authMethod>
          <ns:searchBE>
            <ns1:FromDate>2019-01-01</ns1:FromDate>
            <ns1:Reportee>30014500525</ns1:Reportee>
            <ns1:ToDate>2020-03-16</ns1:ToDate>
          </ns:searchBE>
          <ns:languageID>1033</ns:languageID>
        </ns:GetReporteeElementListBasicV2>
      </soapenv:Body>
    </soapenv:Envelope>