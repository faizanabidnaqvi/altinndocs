---
title: UpdateFormDataBasic
date: 2020-03-14
slug: update-form-data-basic

---
This endpoint is used to attach the RF-1189 form to an existing RF-1030 form (therefore this is an Update Form task rather than submit). Generally, this end point is to add a subform or update an existing main form.

**Input**

systemUserName: External system user name set by the user in their settings  
systemPassword: External system password set by the user in their settings  
userSSN  
userPassword: User's MINID password. (Note that this might depend on the authentication method)  
userPinCode: SMS pin code (this is valid for 30 mins of inactivity)

For each form RF-1189 (usually we only have one),

DataFormatId: 738 (this is always the same as for 2020)  
DataFormatVersion: 12292 or 12162 (2019 and 2018 respectively)

Remember to ensure DataFormatVersion is also set for the attribute spesifikasjonsnummer within the form XML

**Request Example (with an empty but valid RF-1189 form xml)**

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.altinn.no/services/Intermediary/Shipment/IntermediaryInbound/2009/10" xmlns:ns1="http://schemas.altinn.no/services/Intermediary/Shipment/IntermediaryInbound/2018/06">
       <soapenv:Header/>
       <soapenv:Body>
          <ns:UpdateFormDataBasic>
             <ns:systemUserName>hauk_olaussen</ns:systemUserName>
             <ns:systemPassword>password01</ns:systemPassword>
             <ns:userSSN>30014500525</ns:userSSN>
             <ns:userPassword>password01</ns:userPassword>
             <ns:userPinCode>12345</ns:userPinCode>
             <ns:authMethod>AltinnPin</ns:authMethod>
             <ns:formTaskUpdate>
                <ns1:ExternalShipmentReference>EXT_REF${=(int)(Math.random()*100000)}</ns1:ExternalShipmentReference>
                <ns1:FormUpdateList>
                   <!--Zero or more repetitions:-->
                   <ns1:FormUpdate>
                      <ns1:DataFormatId>738</ns1:DataFormatId>
                      <ns1:DataFormatVersion>12162</ns1:DataFormatVersion>
                      <ns1:EndUserSystemReference>1</ns1:EndUserSystemReference>
                      <ns1:FormData><![CDATA[<Skjema xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" skjemanummer="738" spesifikasjonsnummer="12162" blankettnummer="RF-1189" tittel="Årsoppgjør for utleie av fast eiendom" gruppeid="230" etatid="NoAgency" xsi:noNamespaceSchemaLocation="schema%20(1).xsd">
    <GenerellInformasjon-grp-959 gruppeid="959">
     <Avgiver-grp-231 gruppeid="231">
       <OppgavegiverNavn-datadef-68 orid="68">a</OppgavegiverNavn-datadef-68>
       <OppgavegiverFodselsnummer-datadef-26 orid="26">String</OppgavegiverFodselsnummer-datadef-26>
       <EnhetOrganisasjonsnummer-datadef-18 orid="18">String</EnhetOrganisasjonsnummer-datadef-18>
     </Avgiver-grp-231>
    </GenerellInformasjon-grp-959>
    <Eiendom-grp-2168 gruppeid="2168">
     <OpplysningerOmEiendomen-grp-5333 gruppeid="5333">
       <OppgavegiverLand-datadef-34071 orid="34071">a</OppgavegiverLand-datadef-34071>
       <EiendomAdresse-datadef-2019 orid="2019">a</EiendomAdresse-datadef-2019>
       <EiendomGardsnummer-datadef-30514 orid="30514">0</EiendomGardsnummer-datadef-30514>
       <EiendomBruksnummer-datadef-30515 orid="30515">0</EiendomBruksnummer-datadef-30515>
       <EiendomSeksjonsnummer-datadef-30516 orid="30516">0</EiendomSeksjonsnummer-datadef-30516>
       <EiendomAndelsnummer-datadef-37196 orid="37196">0</EiendomAndelsnummer-datadef-37196>
       <BoligselskapNavnSpesifisert-datadef-6829 orid="6829">a</BoligselskapNavnSpesifisert-datadef-6829>
       <BoligselskapOrgansisasjonsnummer-datadef-37197 orid="37197">String</BoligselskapOrgansisasjonsnummer-datadef-37197>
       <EiendomKommuneNummer-datadef-23 orid="23">String</EiendomKommuneNummer-datadef-23>
       <EierSameieAndel-datadef-28168 orid="28168">0</EierSameieAndel-datadef-28168>
     </OpplysningerOmEiendomen-grp-5333>
    </Eiendom-grp-2168>
    <InntekterUtleieverdi-grp-960 gruppeid="960">
     <Utleie-grp-4939 gruppeid="4939">
       <EiendomUtleieTypeSpesifisertEiendom-datadef-22008 orid="22008">forretning</EiendomUtleieTypeSpesifisertEiendom-datadef-22008>
       <LeietakerNavnSpesifisertLeietaker-datadef-22009 orid="22009">a</LeietakerNavnSpesifisertLeietaker-datadef-22009>
       <UtleieEtasjeSpesifisertEiendom-datadef-22010 orid="22010">a</UtleieEtasjeSpesifisertEiendom-datadef-22010>
       <UtleieArealSpesifisertEiendom-datadef-22011 orid="22011">a</UtleieArealSpesifisertEiendom-datadef-22011>
       <UtleieFraDatoSpesifisertEiendom-datadef-22012 orid="22012">1957-08-13</UtleieFraDatoSpesifisertEiendom-datadef-22012>
       <UtleieTilDatoSpesifisertEiendom-datadef-22013 orid="22013">1957-08-13</UtleieTilDatoSpesifisertEiendom-datadef-22013>
       <UtleieInntektSpesifisertEiendom-datadef-22014 orid="22014">0</UtleieInntektSpesifisertEiendom-datadef-22014>
     </Utleie-grp-4939>
     <Kar-grp-4942 gruppeid="4942">
       <EgenleieKarNavn-datadef-22021 orid="22021">a</EgenleieKarNavn-datadef-22021>
       <KarboligStorrelse-datadef-31749 orid="31749">Under_60</KarboligStorrelse-datadef-31749>
       <KarboligManglerBadDusjWc-datadef-31750 orid="31750">Nei</KarboligManglerBadDusjWc-datadef-31750>
       <KontaktVilkarEndret-datadef-32925 orid="32925">Ja</KontaktVilkarEndret-datadef-32925>
       <EgenleieKarInntekt-datadef-22026 orid="22026">0</EgenleieKarInntekt-datadef-22026>
     </Kar-grp-4942>
     <VedlikeholdskostnaderMvLeietakere-datadef-22032 orid="22032">0</VedlikeholdskostnaderMvLeietakere-datadef-22032>
     <InntekterAndre-datadef-22101 orid="22101">0</InntekterAndre-datadef-22101>
     <BruttoinntektUtleieMv-datadef-22033 orid="22033">0</BruttoinntektUtleieMv-datadef-22033>
    </InntekterUtleieverdi-grp-960>
    <Kostnader-grp-236 gruppeid="236">
     <Festeavgift-grp-5281 gruppeid="5281">
       <Festeavgift-datadef-7885 orid="7885">0</Festeavgift-datadef-7885>
       <FesteavgiftFradragsbrettiget-datadef-23634 orid="23634">0</FesteavgiftFradragsbrettiget-datadef-23634>
     </Festeavgift-grp-5281>
     <KommunaleAvgifter-grp-5282 gruppeid="5282">
       <AvgifterEiendomKommunale-datadef-7886 orid="7886">0</AvgifterEiendomKommunale-datadef-7886>
       <AvgifterEiendomKommunaleFradragsberretiget-datadef-23635 orid="23635">0</AvgifterEiendomKommunaleFradragsberretiget-datadef-23635>
     </KommunaleAvgifter-grp-5282>
     <Lonnskostnader-grp-5283 gruppeid="5283">
       <LonnsoppgaveInnsendt-datadef-7908 orid="7908">Nei</LonnsoppgaveInnsendt-datadef-7908>
       <DriftsutgifterVaktmesterBestyrerDisponentForretningsforer-datadef-7889 orid="7889">0</DriftsutgifterVaktmesterBestyrerDisponentForretningsforer-datadef-7889>
       <DriftsutgifterVaktmesterBestyrerDisponentMvFradragsberretiget-datadef-23636 orid="23636">0</DriftsutgifterVaktmesterBestyrerDisponentMvFradragsberretiget-datadef-23636>
     </Lonnskostnader-grp-5283>
     <DriftsutgifterEiendomAvgifterLonnSkattemessig-datadef-23637 orid="23637">0</DriftsutgifterEiendomAvgifterLonnSkattemessig-datadef-23637>
     <VedlikeholdPakostningerForandringerMv-grp-3488 gruppeid="3488">
       <VedlikeholdMv-grp-237 gruppeid="237">
         <EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898 orid="7898">a</EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898>
         <OppdragstakerNavnSpesifisertVedlikehold-datadef-7899 orid="7899">a</OppdragstakerNavnSpesifisertVedlikehold-datadef-7899>
         <OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900 orid="7900">a</OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900>
         <OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901 orid="7901">String</OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901>
         <OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902 orid="7902">a</OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902>
         <EiendomVedlikeholdDatoSpesifisert-datadef-7903 orid="7903">1957-08-13</EiendomVedlikeholdDatoSpesifisert-datadef-7903>
         <DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904 orid="7904">0</DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904>
         <DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905 orid="7905">0</DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905>
       </VedlikeholdMv-grp-237>
       <DriftsutgifterEiendomVedlikeholdFradragsberettiget-datadef-7906 orid="7906">0</DriftsutgifterEiendomVedlikeholdFradragsberettiget-datadef-7906>
       <DriftsutgifterEiendomVedlikeholdReduksjon-datadef-7907 orid="7907">2</DriftsutgifterEiendomVedlikeholdReduksjon-datadef-7907>
       <DriftsutgifterEiendomVedlikeholdSkattemessig-datadef-7890 orid="7890">0</DriftsutgifterEiendomVedlikeholdSkattemessig-datadef-7890>
     </VedlikeholdPakostningerForandringerMv-grp-3488>
     <DriftsutgifterUtleieTap-datadef-7892 orid="7892">0</DriftsutgifterUtleieTap-datadef-7892>
     <BygningUtleieAvskrivningBelop-datadef-22034 orid="22034">0</BygningUtleieAvskrivningBelop-datadef-22034>
     <AndreKostnader-grp-971 gruppeid="971">
       <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
         <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">a</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
         <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">0</DriftsutgifterAndreSpesifisert-datadef-10069>
       </AndreKostnaderSpesifisert-grp-4944>
       <DriftsutgifterLysBrenselRenholdEgenBoligdel-datadef-7896 orid="7896">0</DriftsutgifterLysBrenselRenholdEgenBoligdel-datadef-7896>
       <DriftsutgifterEgenBoligdel-datadef-22102 orid="22102">0</DriftsutgifterEgenBoligdel-datadef-22102>
     </AndreKostnader-grp-971>
     <UtgifterFastEiendom-datadef-7918 orid="7918">0</UtgifterFastEiendom-datadef-7918>
    </Kostnader-grp-236>
    <Nettoinntekt-grp-4945 gruppeid="4945">
     <InntektNetto-datadef-28169 orid="28169">0</InntektNetto-datadef-28169>
     <InntektOverfortEktefelle-datadef-28170 orid="28170">0</InntektOverfortEktefelle-datadef-28170>
     <LeieinntekterNettoOverskudd-datadef-7897 orid="7897">0</LeieinntekterNettoOverskudd-datadef-7897>
     <LeieinntekterNettoUnderskudd-datadef-14188 orid="14188">0</LeieinntekterNettoUnderskudd-datadef-14188>
    </Nettoinntekt-grp-4945>
    <Kontrollsporsmal-grp-239 gruppeid="239">
     <OmfatterKostnadeneNoeAvFolgende-grp-2330 gruppeid="2330">
       <UtgifterSkattFormueInntekt-datadef-7911 orid="7911">Nei</UtgifterSkattFormueInntekt-datadef-7911>
       <UtgifterSkatterFormueInntektBelop-datadef-7912 orid="7912">0</UtgifterSkatterFormueInntektBelop-datadef-7912>
       <UtgifterGodtgjoringHuseierMv-datadef-7913 orid="7913">Ja</UtgifterGodtgjoringHuseierMv-datadef-7913>
       <UtgifterGodtgjoringHuseierMvBelop-datadef-7914 orid="7914">0</UtgifterGodtgjoringHuseierMvBelop-datadef-7914>
       <UtgifterKontingentHuseierforeninger-datadef-7915 orid="7915">Nei</UtgifterKontingentHuseierforeninger-datadef-7915>
       <UtgifterKontingentHuseierforeningerBelop-datadef-7916 orid="7916">0</UtgifterKontingentHuseierforeningerBelop-datadef-7916>
     </OmfatterKostnadeneNoeAvFolgende-grp-2330>
    </Kontrollsporsmal-grp-239>
    </Skjema>
    ]]></ns1:FormData>
                      <!--Optional:-->
                      <ns1:FormId>0</ns1:FormId>
                   </ns1:FormUpdate>
                </ns1:FormUpdateList>
                <ns1:ReporteeElementId>7992038</ns1:ReporteeElementId>
             </ns:formTaskUpdate>
          </ns:UpdateFormDataBasic>
       </soapenv:Body>
    </soapenv:Envelope>

**Response Example (Success)**

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <UpdateFormDataBasicResponse xmlns="http://www.altinn.no/services/Intermediary/Shipment/IntermediaryInbound/2009/10">
             <UpdateFormDataBasicResult xmlns:a="http://schemas.altinn.no/services/Intermediary/Receipt/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:LastChanged>2020-03-16T03:02:03.903</a:LastChanged>
                <a:ParentReceiptId>0</a:ParentReceiptId>
                <a:ReceiptHistory>Mar 16 2020  1:46AM - OK - 1/1 forms updated. 0 forms failed validation.
    Jan 10 2020  1:45PM - OK - 1/1 forms updated. 0 forms failed validation.
    Jan 10 2020  1:44PM - OK - 0/1 forms updated. 1 forms failed validation.
    Jan 10 2020  1:42PM - OK - 0/1 forms updated. 1 forms failed validation.</a:ReceiptHistory>
                <a:ReceiptId>28362770</a:ReceiptId>
                <a:ReceiptStatusCode>OK</a:ReceiptStatusCode>
                <a:ReceiptText>1/1 forms updated. 0 forms failed validation.</a:ReceiptText>
                <a:ReceiptTypeName>FormTask</a:ReceiptTypeName>
                <a:References>
                   <a:Reference>
                      <a:ReferenceTypeName>ExternalShipmentReference</a:ReferenceTypeName>
                      <a:ReferenceValue>EXT_REF5157</a:ReferenceValue>
                   </a:Reference>
                   <a:Reference>
                      <a:ReferenceTypeName>WorkFlowReference</a:ReferenceTypeName>
                      <a:ReferenceValue>7992038</a:ReferenceValue>
                   </a:Reference>
                   <a:Reference>
                      <a:ReferenceTypeName>OwnerPartyReference</a:ReferenceTypeName>
                      <a:ReferenceValue>30014500525</a:ReferenceValue>
                   </a:Reference>
                </a:References>
                <a:SubReceipts>
                   <a:ReceiptExternal>
                      <a:LastChanged>2020-03-16T03:02:03.903</a:LastChanged>
                      <a:ParentReceiptId>28362770</a:ParentReceiptId>
                      <a:ReceiptHistory>Mar 16 2020  1:46AM - OK - FormId 5739688 was successfully created/updated
    Jan 10 2020  1:45PM - OK - FormId 5562298 was successfully created/updated
    Jan 10 2020  1:44PM - ValidationFailed - Error: &lt;SchemaValidationError>The value of the 'spesifikasjonsnummer' attribute does not equal its fixed value.&lt;/SchemaValidationError> :  Error path: 
    
    Jan 10 2020  1:42PM - ValidationFailed - Error: &lt;SchemaValidationError>The value of the 'spesifikasjonsnummer' attribute does not equal its fixed value.&lt;/SchemaValidationError> :  Error path:</a:ReceiptHistory>
                      <a:ReceiptId>28362771</a:ReceiptId>
                      <a:ReceiptStatusCode>OK</a:ReceiptStatusCode>
                      <a:ReceiptText>FormId 5739781 was successfully created/updated</a:ReceiptText>
                      <a:ReceiptTypeName>FormTask</a:ReceiptTypeName>
                      <a:References>
                         <a:Reference>
                            <a:ReferenceTypeName>EndUserSystemReference</a:ReferenceTypeName>
                            <a:ReferenceValue>1</a:ReferenceValue>
                         </a:Reference>
                      </a:References>
                      <a:SubReceipts i:nil="true"/>
                   </a:ReceiptExternal>
                </a:SubReceipts>
             </UpdateFormDataBasicResult>
          </UpdateFormDataBasicResponse>
       </s:Body>
    </s:Envelope>

**Response Example (Failed due to incorrect DataFormatID and DataFormatVersion)**

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <UpdateFormDataBasicResponse xmlns="http://www.altinn.no/services/Intermediary/Shipment/IntermediaryInbound/2009/10">
             <UpdateFormDataBasicResult xmlns:a="http://schemas.altinn.no/services/Intermediary/Receipt/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:LastChanged>0001-01-01T00:00:00</a:LastChanged>
                <a:ParentReceiptId>0</a:ParentReceiptId>
                <a:ReceiptHistory i:nil="true"/>
                <a:ReceiptId>0</a:ReceiptId>
                <a:ReceiptStatusCode>Rejected</a:ReceiptStatusCode>
                <a:ReceiptText>Validation of the provided forms failed: Invalid DataFormatId and DataformatVersion for 1</a:ReceiptText>
                <a:ReceiptTypeName>NotSet</a:ReceiptTypeName>
                <a:References i:nil="true"/>
                <a:SubReceipts i:nil="true"/>
             </UpdateFormDataBasicResult>
          </UpdateFormDataBasicResponse>
       </s:Body>
    </s:Envelope>

**Response Example (Failed due to incorrect form xml, wrong spesifikasjonsnummer)**

Note that StatusCode is OK in the main section but says ValidationFailed for ReceiptStatusCode under ReceiptExternal

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <UpdateFormDataBasicResponse xmlns="http://www.altinn.no/services/Intermediary/Shipment/IntermediaryInbound/2009/10">
             <UpdateFormDataBasicResult xmlns:a="http://schemas.altinn.no/services/Intermediary/Receipt/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:LastChanged>2020-03-16T03:20:27.753</a:LastChanged>
                <a:ParentReceiptId>0</a:ParentReceiptId>
                <a:ReceiptHistory>Mar 16 2020  3:02AM - OK - 1/1 forms updated. 0 forms failed validation.
    Mar 16 2020  1:46AM - OK - 1/1 forms updated. 0 forms failed validation.
    Jan 10 2020  1:45PM - OK - 1/1 forms updated. 0 forms failed validation.
    Jan 10 2020  1:44PM - OK - 0/1 forms updated. 1 forms failed validation.
    Jan 10 2020  1:42PM - OK - 0/1 forms updated. 1 forms failed validation.</a:ReceiptHistory>
                <a:ReceiptId>28362770</a:ReceiptId>
                <a:ReceiptStatusCode>OK</a:ReceiptStatusCode>
                <a:ReceiptText>0/1 forms updated. 1 forms failed validation.</a:ReceiptText>
                <a:ReceiptTypeName>FormTask</a:ReceiptTypeName>
                <a:References>
                   <a:Reference>
                      <a:ReferenceTypeName>ExternalShipmentReference</a:ReferenceTypeName>
                      <a:ReferenceValue>EXT_REF5157</a:ReferenceValue>
                   </a:Reference>
                   <a:Reference>
                      <a:ReferenceTypeName>WorkFlowReference</a:ReferenceTypeName>
                      <a:ReferenceValue>7992038</a:ReferenceValue>
                   </a:Reference>
                   <a:Reference>
                      <a:ReferenceTypeName>OwnerPartyReference</a:ReferenceTypeName>
                      <a:ReferenceValue>30014500525</a:ReferenceValue>
                   </a:Reference>
                </a:References>
                <a:SubReceipts>
                   <a:ReceiptExternal>
                      <a:LastChanged>2020-03-16T03:20:27.753</a:LastChanged>
                      <a:ParentReceiptId>28362770</a:ParentReceiptId>
                      <a:ReceiptHistory>Mar 16 2020  3:02AM - OK - FormId 5739781 was successfully created/updated
    Mar 16 2020  1:46AM - OK - FormId 5739688 was successfully created/updated
    Jan 10 2020  1:45PM - OK - FormId 5562298 was successfully created/updated
    Jan 10 2020  1:44PM - ValidationFailed - Error: &lt;SchemaValidationError>The value of the 'spesifikasjonsnummer' attribute does not equal its fixed value.&lt;/SchemaValidationError> :  Error path: 
    
    Jan 10 2020  1:42PM - ValidationFailed - Error: &lt;SchemaValidationError>The value of the 'spesifikasjonsnummer' attribute does not equal its fixed value.&lt;/SchemaValidationError> :  Error path:</a:ReceiptHistory>
                      <a:ReceiptId>28362771</a:ReceiptId>
                      <a:ReceiptStatusCode>ValidationFailed</a:ReceiptStatusCode>
                      <a:ReceiptText>Error: &lt;SchemaValidationError>The value of the 'spesifikasjonsnummer' attribute does not equal its fixed value.&lt;/SchemaValidationError> :  Error path:</a:ReceiptText>
                      <a:ReceiptTypeName>FormTask</a:ReceiptTypeName>
                      <a:References>
                         <a:Reference>
                            <a:ReferenceTypeName>EndUserSystemReference</a:ReferenceTypeName>
                            <a:ReferenceValue>1</a:ReferenceValue>
                         </a:Reference>
                      </a:References>
                      <a:SubReceipts i:nil="true"/>
                   </a:ReceiptExternal>
                </a:SubReceipts>
             </UpdateFormDataBasicResult>
          </UpdateFormDataBasicResponse>
       </s:Body>
    </s:Envelope>

end