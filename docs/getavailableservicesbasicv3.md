---
title: GetAvailableServicesBasicV3
date: 2020-03-13
slug: get-available-services

---
This endpoint is used to find all available services by Altinn. By available services, we generally mean the main forms. In our case, we are only concerned with the RF-1030 services. We use this endpoint to find the possible RF-1030 form's ExternalServiceCode and ServiceEditionVersionId/ServiceEditionVersion. 

These are required so we can search for the right form in the GetReporteeElement output.

At the moment (2019 and 2020), we are only concerned with:

**RF-1030 Skattemelding for formues- og inntektsskatt – lønnstakere og pensjonister**

ExternalServiceCode: 3348

**RF-1030 Skattemelding for formues- og inntektsskatt – personlig næringsdrivende**

ExternalServiceCode: 3349

The ExternalServiceEditionCode output is generally the tax year (e.g. 2019 for 2020). ServiceEditionVersionId/ServiceEditionVersion change per tax year as well.

**Input**

systemUserName: The user name set by the user for external systems in their settings

systemPassword: The password set by the user for external systems in their settings

**Request Example**

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.altinn.no/services/ServiceEngine/ServiceMetaData/2009/10">
       <soapenv:Header/>
       <soapenv:Body>
          <ns:GetAvailableServicesBasicV3>
          <ns:systemUserName>hauk_olaussen</ns:systemUserName>
          <ns:systemPassword>password01</ns:systemPassword>
          </ns:GetAvailableServicesBasicV3>
       </soapenv:Body>
    </soapenv:Envelope>

**Response Example (only showing what we use)**

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <GetAvailableServicesBasicV3Response xmlns="http://www.altinn.no/services/ServiceEngine/ServiceMetaData/2009/10">
             <GetAvailableServicesBasicV3Result xmlns:a="http://schemas.altinn.no/services/ServiceEngine/ServiceMetaData/2013/06" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:AvailableServices>
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
                   <a:AvailableServiceBEV3>
                      <a:AttachmentRuleTypeList i:nil="true"/>
                      <a:BuildPackageVersion>41</a:BuildPackageVersion>
                      <a:ExternalServiceCode>3348</a:ExternalServiceCode>
                      <a:ExternalServiceEditionCode>2019</a:ExternalServiceEditionCode>
                      <a:IsMatched>false</a:IsMatched>
                      <a:ServiceEditionVersionId>180141</a:ServiceEditionVersionId>
                      <a:ServiceEditionVersionName>RF-1030 Skattemelding for formues- og inntektsskatt – lønnstakere og pensjonister mv. 2019</a:ServiceEditionVersionName>
                      <a:ServiceName>RF-1030PSA</a:ServiceName>
                      <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                      <a:ServiceOwnerName>Norwegian Tax Administration</a:ServiceOwnerName>
                      <a:ServiceType>Reporting</a:ServiceType>
                      <a:ValidFrom>2020-02-03T21:21:00</a:ValidFrom>
                      <a:ValidTo>2021-02-01T23:59:00</a:ValidTo>
                   </a:AvailableServiceBEV3>
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
                   <a:AvailableServiceBEV3>
                      <a:AttachmentRuleTypeList i:nil="true"/>
                      <a:BuildPackageVersion>40</a:BuildPackageVersion>
                      <a:ExternalServiceCode>3349</a:ExternalServiceCode>
                      <a:ExternalServiceEditionCode>2019</a:ExternalServiceEditionCode>
                      <a:IsMatched>false</a:IsMatched>
                      <a:ServiceEditionVersionId>180143</a:ServiceEditionVersionId>
                      <a:ServiceEditionVersionName>RF-1030 Skattemelding for formues- og inntektsskatt – personlig næringsdrivende mv. 2019</a:ServiceEditionVersionName>
                      <a:ServiceName>RF-1030PSAN</a:ServiceName>
                      <a:ServiceOwnerCode>SKD</a:ServiceOwnerCode>
                      <a:ServiceOwnerName>Norwegian Tax Administration</a:ServiceOwnerName>
                      <a:ServiceType>Reporting</a:ServiceType>
                      <a:ValidFrom>2020-02-03T21:33:00</a:ValidFrom>
                      <a:ValidTo>2021-02-01T23:59:00</a:ValidTo>
                   </a:AvailableServiceBEV3>
                </a:AvailableServices>
                <a:StatusMessage>2008 services found for specified input parameters.</a:StatusMessage>
             </GetAvailableServicesBasicV3Result>
          </GetAvailableServicesBasicV3Response>
       </s:Body>
    </s:Envelope>

end