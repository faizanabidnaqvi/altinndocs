---
title: GetFormTaskSchemaDefinition
date: 2020-03-13
slug: get-form-task

---
Every service (main form) in Altinn has several possible forms to submit together with it (including the main one). This end point allows us to specify the service code and retrieve the format and additional information for all associated forms.

In our case, we use this to find the XSD, DataFormatID and DataFormatVersion for the latest RF-1189 form (which is a subform to RF-1030) 

**Input**

systemUserName: System user name as specified by the user in their settings  
systemPassword: System password as specified by the user in their settings  
externalServiceCode: The service code for the service (retrieved from the Get Available Services end point)  
externalServiceEditionCode: The service edition code which generally (so far) is the tax year

**Request Example**

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.altinn.no/services/ServiceEngine/ServiceMetaData/2009/10">
       <soapenv:Header/>
       <soapenv:Body>
          <ns:GetFormTaskSchemaDefinitionsBasic>
          <ns:systemUserName>hauk_olaussen</ns:systemUserName>
          <ns:systemPassword>password01</ns:systemPassword>
          <ns:externalServiceCode>3349</ns:externalServiceCode>
          <ns:externalServiceEditionCode>2018</ns:externalServiceEditionCode>
          </ns:GetFormTaskSchemaDefinitionsBasic>
       </soapenv:Body>
    </soapenv:Envelope>

**Response Example (trimmed and CDATA not shown for brevity)**

Output is only shown for RF-1189 related task

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <GetFormTaskSchemaDefinitionsBasicResponse xmlns="http://www.altinn.no/services/ServiceEngine/ServiceMetaData/2009/10">
             <GetFormTaskSchemaDefinitionsBasicResult xmlns:a="http://schemas.altinn.no/services/ServiceEngine/ServiceMetaData/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:LogicalFormSchemaDefinition>
                  <a:DataFormatID>738</a:DataFormatID>
                  <a:DataFormatProviderTypeID>1</a:DataFormatProviderTypeID>
                  <a:DataFormatVersion>12292</a:DataFormatVersion>
                  <a:DataFormatXsd><![CDATA[..xsd..]]></a:DataFormatXsd>
                  <a:LogicalFormID>280698</a:LogicalFormID>
                </a:LogicalFormSchemaDefinition>
             </GetFormTaskSchemaDefinitionsBasicResult>
          </GetFormTaskSchemaDefinitionsBasicResponse>
       </s:Body>
    </s:Envelope>

end