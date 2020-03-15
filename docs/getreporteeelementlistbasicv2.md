---
title: GetReporteeElementListBasicV2
date: 2020-03-13
slug: get-reportee-element-list

---
This endpoint is used to find all the forms in the system.  In our scenario, we will use to find the RF-1030 form we wish to attach RF-1189 to. They can be filtered based on criteria as well.

Before sending this request, we need to find out the systemUserName and systemPassword from the user. This is set by the user in Altinn settings to let external systems access their profile.

**Inputs**

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

Language,

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

**Output**

The return will consist of all the forms whether archives or filled during the period specified in the search. For the app, we are only concerned with RF-1030 forms. _Look at the type of forms in the docs_. Below, we only document output field we might be concerned with.

ExternalServiceCode: This is the service code of the form. Each form type has a service code. For RF-1030, we are concerned with codes 3348 and 3349 which refer to both possible versions of RF-1030.

LastChangedDate: Last date this form was updated.

ReporteeElementId: The unique form ID. THIS IS WHAT WE NEED to find which form we need to attach RF-1189 to.

Status: The status of the form. There are two, FillIn and Archive. Work in progress forms that we need are always FillIn.

StatusName: The current status name of the form. The 'Completion' state refers to work in progress forms; this is the only state of form we need to attach RF-1189 to later. The other state is 'Sent and archived' which is for archived forms.

**Response Example**

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <GetReporteeElementListBasicV2Response xmlns="http://www.altinn.no/services/ServiceEngine/ReporteeElementList/2009/10">
             <GetReporteeElementListBasicV2Result xmlns:a="http://www.altinn.no/services/ServiceEngine/ReporteeElementList/2010/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:ReporteeElementBEV2>
                   <a:AllowDelete>true</a:AllowDelete>
                   <a:AllowNewCopy>true</a:AllowNewCopy>
                   <a:Altinn1ArchiveUnitId i:nil="true"/>
                   <a:Altinn1FormCode i:nil="true"/>
                   <a:Altinn1FormId i:nil="true"/>
                   <a:Altinn1FormInstanceID i:nil="true"/>
                   <a:Altinn1FormORNo i:nil="true"/>
                   <a:Altinn1ParticipantID i:nil="true"/>
                   <a:Altinn1ReferenceType i:nil="true"/>
                   <a:Altinn1WorkflowProcessId i:nil="true"/>
                   <a:ArchiveId i:nil="true"/>
                   <a:ArchiveReference i:nil="true"/>
                   <a:CaseID>0</a:CaseID>
                   <a:CorrespondenceStatus>Default</a:CorrespondenceStatus>
                   <a:DueDate i:nil="true"/>
                   <a:EndUserSystemID>0</a:EndUserSystemID>
                   <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                   <a:IsCaseArchived>false</a:IsCaseArchived>
                   <a:IsMatched>false</a:IsMatched>
                   <a:LastChangeType>Default</a:LastChangeType>
                   <a:LastChangedBy>HAUK OLAUSSEN</a:LastChangedBy>
                   <a:LastChangedByID>62689</a:LastChangedByID>
                   <a:LastChangedDate>2020-03-15T15:23:17.43</a:LastChangedDate>
                   <a:Notice i:nil="true"/>
                   <a:ParentCaseName i:nil="true"/>
                   <a:ReporteeElementId>7992038</a:ReporteeElementId>
                   <a:ReporteeElementOwner>50111027</a:ReporteeElementOwner>
                   <a:ReporteeElementType>FormTask</a:ReporteeElementType>
                   <a:ReporteeName>30014500525 HAUK OLAUSSEN</a:ReporteeName>
                   <a:RoleRequirement>ReadAndPerformNextStep</a:RoleRequirement>
                   <a:RoleRequirementAltinn1Element i:nil="true"/>
                   <a:SEReporteeElementID>0</a:SEReporteeElementID>
                   <a:ServiceEditionVersion>164393</a:ServiceEditionVersion>
                   <a:ServiceOwner>34</a:ServiceOwner>
                   <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                   <a:ServiceOwnerDescription i:nil="true"/>
                   <a:Status>FillIn</a:Status>
                   <a:StatusName>Completion</a:StatusName>
                   <a:TaskStatus>Default</a:TaskStatus>
                   <a:Title>RF-1030 Tax return for wealth and income tax - self-employed individuals 2018</a:Title>
                </a:ReporteeElementBEV2>
                <a:ReporteeElementBEV2>
                   <a:AllowDelete>true</a:AllowDelete>
                   <a:AllowNewCopy>true</a:AllowNewCopy>
                   <a:Altinn1ArchiveUnitId i:nil="true"/>
                   <a:Altinn1FormCode i:nil="true"/>
                   <a:Altinn1FormId i:nil="true"/>
                   <a:Altinn1FormInstanceID i:nil="true"/>
                   <a:Altinn1FormORNo i:nil="true"/>
                   <a:Altinn1ParticipantID i:nil="true"/>
                   <a:Altinn1ReferenceType i:nil="true"/>
                   <a:Altinn1WorkflowProcessId i:nil="true"/>
                   <a:ArchiveId i:nil="true"/>
                   <a:ArchiveReference i:nil="true"/>
                   <a:CaseID>0</a:CaseID>
                   <a:CorrespondenceStatus>Default</a:CorrespondenceStatus>
                   <a:DueDate i:nil="true"/>
                   <a:EndUserSystemID>0</a:EndUserSystemID>
                   <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                   <a:IsCaseArchived>false</a:IsCaseArchived>
                   <a:IsMatched>false</a:IsMatched>
                   <a:LastChangeType>Default</a:LastChangeType>
                   <a:LastChangedBy>HAUK OLAUSSEN</a:LastChangedBy>
                   <a:LastChangedByID>62689</a:LastChangedByID>
                   <a:LastChangedDate>2019-05-12T11:17:53.36</a:LastChangedDate>
                   <a:Notice i:nil="true"/>
                   <a:ParentCaseName i:nil="true"/>
                   <a:ReporteeElementId>7012694</a:ReporteeElementId>
                   <a:ReporteeElementOwner>50111027</a:ReporteeElementOwner>
                   <a:ReporteeElementType>FormTask</a:ReporteeElementType>
                   <a:ReporteeName>30014500525 HAUK OLAUSSEN</a:ReporteeName>
                   <a:RoleRequirement>ReadAndPerformNextStep</a:RoleRequirement>
                   <a:RoleRequirementAltinn1Element i:nil="true"/>
                   <a:SEReporteeElementID>0</a:SEReporteeElementID>
                   <a:ServiceEditionVersion>142270</a:ServiceEditionVersion>
                   <a:ServiceOwner>34</a:ServiceOwner>
                   <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                   <a:ServiceOwnerDescription i:nil="true"/>
                   <a:Status>FillIn</a:Status>
                   <a:StatusName>Completion</a:StatusName>
                   <a:TaskStatus>Default</a:TaskStatus>
                   <a:Title>RF-1030 Tax return for wealth and income tax - self-employed individuals 2017</a:Title>
                </a:ReporteeElementBEV2>
                <a:ReporteeElementBEV2>
                   <a:AllowDelete>true</a:AllowDelete>
                   <a:AllowNewCopy>true</a:AllowNewCopy>
                   <a:Altinn1ArchiveUnitId i:nil="true"/>
                   <a:Altinn1FormCode i:nil="true"/>
                   <a:Altinn1FormId i:nil="true"/>
                   <a:Altinn1FormInstanceID i:nil="true"/>
                   <a:Altinn1FormORNo i:nil="true"/>
                   <a:Altinn1ParticipantID i:nil="true"/>
                   <a:Altinn1ReferenceType i:nil="true"/>
                   <a:Altinn1WorkflowProcessId i:nil="true"/>
                   <a:ArchiveId i:nil="true"/>
                   <a:ArchiveReference i:nil="true"/>
                   <a:CaseID>0</a:CaseID>
                   <a:CorrespondenceStatus>Default</a:CorrespondenceStatus>
                   <a:DueDate i:nil="true"/>
                   <a:EndUserSystemID>0</a:EndUserSystemID>
                   <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                   <a:IsCaseArchived>false</a:IsCaseArchived>
                   <a:IsMatched>false</a:IsMatched>
                   <a:LastChangeType>Default</a:LastChangeType>
                   <a:LastChangedBy>HAUK OLAUSSEN</a:LastChangedBy>
                   <a:LastChangedByID>62689</a:LastChangedByID>
                   <a:LastChangedDate>2020-03-15T13:06:47.233</a:LastChangedDate>
                   <a:Notice i:nil="true"/>
                   <a:ParentCaseName i:nil="true"/>
                   <a:ReporteeElementId>8651544</a:ReporteeElementId>
                   <a:ReporteeElementOwner>50111027</a:ReporteeElementOwner>
                   <a:ReporteeElementType>FormTask</a:ReporteeElementType>
                   <a:ReporteeName>30014500525 HAUK OLAUSSEN</a:ReporteeName>
                   <a:RoleRequirement>ReadAndPerformNextStep</a:RoleRequirement>
                   <a:RoleRequirementAltinn1Element i:nil="true"/>
                   <a:SEReporteeElementID>0</a:SEReporteeElementID>
                   <a:ServiceEditionVersion>180143</a:ServiceEditionVersion>
                   <a:ServiceOwner>34</a:ServiceOwner>
                   <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                   <a:ServiceOwnerDescription i:nil="true"/>
                   <a:Status>FillIn</a:Status>
                   <a:StatusName>Completion</a:StatusName>
                   <a:TaskStatus>Default</a:TaskStatus>
                   <a:Title>RF-1030 Tax return for wealth and income tax - self-employed individuals 2019</a:Title>
                </a:ReporteeElementBEV2>
                <a:ReporteeElementBEV2>
                   <a:AllowDelete>true</a:AllowDelete>
                   <a:AllowNewCopy>true</a:AllowNewCopy>
                   <a:Altinn1ArchiveUnitId i:nil="true"/>
                   <a:Altinn1FormCode i:nil="true"/>
                   <a:Altinn1FormId i:nil="true"/>
                   <a:Altinn1FormInstanceID i:nil="true"/>
                   <a:Altinn1FormORNo i:nil="true"/>
                   <a:Altinn1ParticipantID i:nil="true"/>
                   <a:Altinn1ReferenceType i:nil="true"/>
                   <a:Altinn1WorkflowProcessId i:nil="true"/>
                   <a:ArchiveId>5276128</a:ArchiveId>
                   <a:ArchiveReference>AR5276128</a:ArchiveReference>
                   <a:CaseID>0</a:CaseID>
                   <a:CorrespondenceStatus>Default</a:CorrespondenceStatus>
                   <a:DueDate i:nil="true"/>
                   <a:EndUserSystemID>0</a:EndUserSystemID>
                   <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                   <a:IsCaseArchived>false</a:IsCaseArchived>
                   <a:IsMatched>false</a:IsMatched>
                   <a:LastChangeType>Default</a:LastChangeType>
                   <a:LastChangedBy>Norwegian Tax Administration</a:LastChangedBy>
                   <a:LastChangedByID>0</a:LastChangedByID>
                   <a:LastChangedDate>2019-01-20T20:02:03.227</a:LastChangedDate>
                   <a:Notice i:nil="true"/>
                   <a:ParentCaseName i:nil="true"/>
                   <a:ReporteeElementId>0</a:ReporteeElementId>
                   <a:ReporteeElementOwner>50111027</a:ReporteeElementOwner>
                   <a:ReporteeElementType>FormTask</a:ReporteeElementType>
                   <a:ReporteeName>30014500525 HAUK OLAUSSEN</a:ReporteeName>
                   <a:RoleRequirement>Default</a:RoleRequirement>
                   <a:RoleRequirementAltinn1Element i:nil="true"/>
                   <a:SEReporteeElementID>7012668</a:SEReporteeElementID>
                   <a:ServiceEditionVersion>142270</a:ServiceEditionVersion>
                   <a:ServiceOwner>34</a:ServiceOwner>
                   <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                   <a:ServiceOwnerDescription i:nil="true"/>
                   <a:Status>Archive</a:Status>
                   <a:StatusName>Sent and archived</a:StatusName>
                   <a:TaskStatus>Default</a:TaskStatus>
                   <a:Title>RF-1030 Tax return for wealth and income tax - self-employed individuals 2017</a:Title>
                </a:ReporteeElementBEV2>
                <a:ReporteeElementBEV2>
                   <a:AllowDelete>true</a:AllowDelete>
                   <a:AllowNewCopy>true</a:AllowNewCopy>
                   <a:Altinn1ArchiveUnitId i:nil="true"/>
                   <a:Altinn1FormCode i:nil="true"/>
                   <a:Altinn1FormId i:nil="true"/>
                   <a:Altinn1FormInstanceID i:nil="true"/>
                   <a:Altinn1FormORNo i:nil="true"/>
                   <a:Altinn1ParticipantID i:nil="true"/>
                   <a:Altinn1ReferenceType i:nil="true"/>
                   <a:Altinn1WorkflowProcessId i:nil="true"/>
                   <a:ArchiveId>5276126</a:ArchiveId>
                   <a:ArchiveReference>AR5276126</a:ArchiveReference>
                   <a:CaseID>0</a:CaseID>
                   <a:CorrespondenceStatus>Default</a:CorrespondenceStatus>
                   <a:DueDate i:nil="true"/>
                   <a:EndUserSystemID>0</a:EndUserSystemID>
                   <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                   <a:IsCaseArchived>false</a:IsCaseArchived>
                   <a:IsMatched>false</a:IsMatched>
                   <a:LastChangeType>Default</a:LastChangeType>
                   <a:LastChangedBy>Norwegian Tax Administration</a:LastChangedBy>
                   <a:LastChangedByID>0</a:LastChangedByID>
                   <a:LastChangedDate>2019-01-20T20:01:43.197</a:LastChangedDate>
                   <a:Notice i:nil="true"/>
                   <a:ParentCaseName i:nil="true"/>
                   <a:ReporteeElementId>0</a:ReporteeElementId>
                   <a:ReporteeElementOwner>50111027</a:ReporteeElementOwner>
                   <a:ReporteeElementType>FormTask</a:ReporteeElementType>
                   <a:ReporteeName>30014500525 HAUK OLAUSSEN</a:ReporteeName>
                   <a:RoleRequirement>Default</a:RoleRequirement>
                   <a:RoleRequirementAltinn1Element i:nil="true"/>
                   <a:SEReporteeElementID>7012690</a:SEReporteeElementID>
                   <a:ServiceEditionVersion>142270</a:ServiceEditionVersion>
                   <a:ServiceOwner>34</a:ServiceOwner>
                   <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                   <a:ServiceOwnerDescription i:nil="true"/>
                   <a:Status>Archive</a:Status>
                   <a:StatusName>Sent and archived</a:StatusName>
                   <a:TaskStatus>Default</a:TaskStatus>
                   <a:Title>RF-1030 Tax return for wealth and income tax - self-employed individuals 2017</a:Title>
                </a:ReporteeElementBEV2>
             </GetReporteeElementListBasicV2Result>
          </GetReporteeElementListBasicV2Response>
       </s:Body>
    </s:Envelope>

end