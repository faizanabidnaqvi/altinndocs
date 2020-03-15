---
title: forms-2019
date: 2020-03-13
slug: forms-2019

---
Here we document ONLY the latest forms and form information available for the year 2019. Note that the year is 2019 but the forms to be submitted will be 2018.

## **Available Services**

The output here is a subset of the output obtained from the GetAvailableServicesBasicV3 endpoint. The subset refers to only the forms we need.

**Summary**

To find a particular form in GetReporteeElement end point based on the current year, we only need to use ExternalServiceCode and ServiceEditionVersionId (which is referred to as ServiceEditionVersion in xml output for GetReporteeElement)

**RF-1030 Skattemelding for formues- og inntektsskatt – lønnstakere og pensjonister mv. 2018 (for wage earners and pension earners)**

ExternalServiceCode: 3348  
ExternalServiceEditionCode: 2018  
ServiceEditionVersionId: 164387 (Note: In GetReporteeElement forms this corresponds to a:ServiceEditionVersion)

**RF-1030 Skattemelding for formues- og inntektsskatt – personlig næringsdrivende mv. 2018 (for business owners)**

ExternalServiceCode: 3349  
ExternalServiceEditionCode: 2018  
ServiceEditionVersionId: 164393 (Note: In GetReporteeElement forms this corresponds to a:ServiceEditionVersion)

**Raw Output**

**RF-1030 Skattemelding for formues- og inntektsskatt – lønnstakere og pensjonister mv. 2018 (for wage earners and pension earners)**

    <a:AvailableServiceBEV3>
      <a:AttachmentRuleTypeList i:nil="true"/>
      <a:BuildPackageVersion>95</a:BuildPackageVersion>
      <a:ExternalServiceCode>3348</a:ExternalServiceCode>
      <a:ExternalServiceEditionCode>2018</a:ExternalServiceEditionCode>
      <a:IsMatched>false</a:IsMatched>
      <a:ServiceEditionVersionId>164387</a:ServiceEditionVersionId>
      <a:ServiceEditionVersionName>RF-1030 Skattemelding for formues- og inntektsskatt – lønnstakere og pensjonister mv. 2018</a:ServiceEditionVersionName>
      <a:ServiceName>RF-1030PSA</a:ServiceName>
      <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
      <a:ServiceOwnerName>Norwegian Tax Administration</a:ServiceOwnerName>
      <a:ServiceType>Reporting</a:ServiceType>
      <a:ValidFrom>2019-03-15T12:47:00</a:ValidFrom>
      <a:ValidTo>2020-03-15T23:59:00</a:ValidTo>
    </a:AvailableServiceBEV3>

**RF-1030 Skattemelding for formues- og inntektsskatt – personlig næringsdrivende mv. 2018 (for business owners)**

    <a:AvailableServiceBEV3>
      <a:AttachmentRuleTypeList i:nil="true"/>
      <a:BuildPackageVersion>87</a:BuildPackageVersion>
      <a:ExternalServiceCode>3349</a:ExternalServiceCode>
      <a:ExternalServiceEditionCode>2018</a:ExternalServiceEditionCode>
      <a:IsMatched>false</a:IsMatched>
      <a:ServiceEditionVersionId>164393</a:ServiceEditionVersionId>
      <a:ServiceEditionVersionName>RF-1030 Skattemelding for formues- og inntektsskatt – personlig næringsdrivende mv. 2018</a:ServiceEditionVersionName>
      <a:ServiceName>RF-1030PSAN</a:ServiceName>
      <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
      <a:ServiceOwnerName>Norwegian Tax Administration</a:ServiceOwnerName>
      <a:ServiceType>Reporting</a:ServiceType>
      <a:ValidFrom>2019-03-15T12:51:00</a:ValidFrom>
      <a:ValidTo>2020-03-15T23:59:00</a:ValidTo>
    </a:AvailableServiceBEV3>

## Form Schema (RF-1189)

The output here is a subset of the output available from the GetFormTaskSchemaDefinition in relation to RF-1189. This was found by finding the text 'RF-1189' in the xml output as it is a lot.

**Summary**

When we submit the RF-1189 form, we need the DataFormatID and DataFormatVersion for the form for the input. The DataFormatVersion can change every year (DataFormatID might as well but it didn't happen for 2020).

DataFormatID: 738  
DataFormatVersion: 12162

**Raw Schema (only for RF-1189) with Xsd omitted. The Xsd is long so it is saved seperately.**

    <a:LogicalFormSchemaDefinition>
                   <a:DataFormatID>738</a:DataFormatID>
                   <a:DataFormatProviderTypeID>1</a:DataFormatProviderTypeID>
                   <a:DataFormatVersion>12162</a:DataFormatVersion>
                   <a:DataFormatXsd><![CDATA[..xsd..]]></a:DataFormatXsd>
                   <a:LogicalFormID>259984</a:LogicalFormID>
    </a:LogicalFormSchemaDefinition>

end