---
title: RF-1189 Examples
date: 2020-03-14
slug: rf-1189-examples

---
Here we show populated XML based on the RF-1189 XSD template. Both of the following apply to 2019 and 2018 tax year.

## Empty Form

An empty form (note that skjemanummer is set to the DataFormatVersion). Using this will show an entirely empty form.

This example is for a 2019 and 2018 form.

    <Skjema xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" skjemanummer="738" spesifikasjonsnummer="12292" blankettnummer="RF-1189" tittel="Årsoppgjør for utleie av fast eiendom" gruppeid="230" etatid="NoAgency" xsi:noNamespaceSchemaLocation="schema%20(1).xsd">
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

## Filled Form

This form is filled for a property and set to 12292 (based on 2019 tax year RF-1189) with comments to explain each field.

    <?xml version="1.0" encoding="UTF-8"?>
    <Skjema xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" skjemanummer="738" spesifikasjonsnummer="12292" blankettnummer="RF-1189" tittel="Årsoppgjør for utleie av fast eiendom" gruppeid="230" etatid="NoAgency" xsi:noNamespaceSchemaLocation="schema%20(1).xsd">
       <GenerellInformasjon-grp-959 gruppeid="959">
          <!-- intro section -->
          <Avgiver-grp-231 gruppeid="231">
             <OppgavegiverNavn-datadef-68 orid="68">HAUK OLAUSSEN</OppgavegiverNavn-datadef-68>
             <!--Element: Name-->
             <OppgavegiverFodselsnummer-datadef-26 orid="26">30014500525</OppgavegiverFodselsnummer-datadef-26>
             <!--Element: id, Fødselsnummer-->
             <EnhetOrganisasjonsnummer-datadef-18 orid="18" xsi:nil="true" />
             <!--Element: organisation number, set to nil if not available-->
          </Avgiver-grp-231>
       </GenerellInformasjon-grp-959>
       <!-- property info section -->
       <Eiendom-grp-2168 gruppeid="2168">
          <OpplysningerOmEiendomen-grp-5333 gruppeid="5333">
             <!-- property address -->
             <OppgavegiverLand-datadef-34071 orid="34071">000</OppgavegiverLand-datadef-34071>
             <!-- Element: country code, 000 is Norway -->
             <EiendomAdresse-datadef-2019 orid="2019">Oscarsgate 12</EiendomAdresse-datadef-2019>
             <!-- Element: Property Street Address -->
             <EiendomGardsnummer-datadef-30514 orid="30514">10</EiendomGardsnummer-datadef-30514>
             <!-- Element: Property Gårdsnr some courtyard number, in altin this is auto retrieved -->
             <EiendomBruksnummer-datadef-30515 orid="30515">53</EiendomBruksnummer-datadef-30515>
             <!-- Element: Property Bruksnr. number (Title no.), in altin this is auto retrieved MAYBE -->
             <EiendomSeksjonsnummer-datadef-30516 orid="30516" xsi:nil="true" />
             <!-- Element: Property Seksjonsnr. number (Section no.), in altin this is auto retrieved MAYBE -->
             <EiendomAndelsnummer-datadef-37196 orid="37196" xsi:nil="true" />
             <!-- Element: Property Andelsnr number , set to nil if not available -->
             <BoligselskapNavnSpesifisert-datadef-6829 orid="6829" xsi:nil="true" />
             <!-- Element: Property Boligselskapets navn (Housing company name), set to nil if not available -->
             <BoligselskapOrgansisasjonsnummer-datadef-37197 orid="37197" xsi:nil="true" />
             <!-- Element: Property Boligselskapets org.nr. (Housing company's org.), set to nil if not available -->
             <EiendomKommuneNummer-datadef-23 orid="23">2003</EiendomKommuneNummer-datadef-23>
             <!-- Element: Property Kommunenr, likely Municipal code which we need to figure how to retrieve. E.g. vadso is 2003 -->
             <EierSameieAndel-datadef-28168 orid="28168">100</EierSameieAndel-datadef-28168>
          </OpplysningerOmEiendomen-grp-5333>
          <!-- Element: Property Percentage Share of owner -->
       </Eiendom-grp-2168>
       <InntekterUtleieverdi-grp-960 gruppeid="960">
          <!-- Revenue Section -->
          <Utleie-grp-4939 gruppeid="4939">
             <!-- Tenant Info and Revenue Group. Each group added per tenant; in altinn these show as a row -->
             <EiendomUtleieTypeSpesifisertEiendom-datadef-22008 orid="22008">bolig</EiendomUtleieTypeSpesifisertEiendom-datadef-22008>
             <!-- Element: Property Type. Select from following: ['bolig', 'fritidseiendom', 'industri', 'forretning', 'tomt', 'annet']  -->
             <LeietakerNavnSpesifisertLeietaker-datadef-22009 orid="22009">Mads Wickstrøm</LeietakerNavnSpesifisertLeietaker-datadef-22009>
             <!-- Element: Tenants Name -->
             <UtleieEtasjeSpesifisertEiendom-datadef-22010 orid="22010">2</UtleieEtasjeSpesifisertEiendom-datadef-22010>
             <!-- Element: Story (Etasje) -->
             <UtleieArealSpesifisertEiendom-datadef-22011 orid="22011">80</UtleieArealSpesifisertEiendom-datadef-22011>
             <!-- Element: sqm (Antall kvm) -->
             <UtleieFraDatoSpesifisertEiendom-datadef-22012 orid="22012">2017-01-01</UtleieFraDatoSpesifisertEiendom-datadef-22012>
             <!-- Element: Rent Start Date from (Fra dato) -->
             <UtleieTilDatoSpesifisertEiendom-datadef-22013 orid="22013">2017-12-31</UtleieTilDatoSpesifisertEiendom-datadef-22013>
             <!-- Element: Rent End Date to (Fra dato) -->
             <UtleieInntektSpesifisertEiendom-datadef-22014 orid="22014">132000</UtleieInntektSpesifisertEiendom-datadef-22014>
             <!-- Element: Revenue from Tenant (Beløp) -->
          </Utleie-grp-4939>
          <Utleie-grp-4939 gruppeid="4939">
             <!--Another tenants info-->
             <EiendomUtleieTypeSpesifisertEiendom-datadef-22008 orid="22008">bolig</EiendomUtleieTypeSpesifisertEiendom-datadef-22008>
             <LeietakerNavnSpesifisertLeietaker-datadef-22009 orid="22009">Jannike Adolfss</LeietakerNavnSpesifisertLeietaker-datadef-22009>
             <UtleieEtasjeSpesifisertEiendom-datadef-22010 orid="22010">1</UtleieEtasjeSpesifisertEiendom-datadef-22010>
             <UtleieArealSpesifisertEiendom-datadef-22011 orid="22011">65</UtleieArealSpesifisertEiendom-datadef-22011>
             <UtleieFraDatoSpesifisertEiendom-datadef-22012 orid="22012">2017-01-01</UtleieFraDatoSpesifisertEiendom-datadef-22012>
             <UtleieTilDatoSpesifisertEiendom-datadef-22013 orid="22013">2017-12-31</UtleieTilDatoSpesifisertEiendom-datadef-22013>
             <UtleieInntektSpesifisertEiendom-datadef-22014 orid="22014">100800</UtleieInntektSpesifisertEiendom-datadef-22014>
          </Utleie-grp-4939>
          <Kar-grp-4942 gruppeid="4942">
             <!--This represents student residence info-->
             <EgenleieKarNavn-datadef-22021 orid="22021" xsi:nil="true" />
             <!--Element: Kårmottakerens navn (Corps recipient's name), set to nil if not available-->
             <KarboligStorrelse-datadef-31749 orid="31749" xsi:nil="true" />
             <!--Element: Kårboligens bruksareal er: (Kårbolig's utility area is:), set to nil if not available, possible values: ['Over_100','60_til_100','Under_60']-->
             <KarboligManglerBadDusjWc-datadef-31750 orid="31750" xsi:nil="true" />
             <!--Element: Mangler kårboligen bade-/dusjrom eller wc? (Lack of corridor bath / shower room or wc?), set to nil if not available, possible values ['Ja','Nei']-->
             <KontaktVilkarEndret-datadef-32925 orid="32925" xsi:nil="true" />
             <!--Element: Has the contract ended? (Er kårkontrakten endret?), set to nil if not available, possible values ['Ja','Nei']-->
             <EgenleieKarInntekt-datadef-22026 orid="22026" xsi:nil="true" />
             <!--Element: Revenue from residence (Beløp) -->
          </Kar-grp-4942>
          <VedlikeholdskostnaderMvLeietakere-datadef-22032 orid="22032" xsi:nil="true" />
          <!--Element: Refusjon fra leietakere for vedlikeholdskostnader mv. (Refunds from tenants for maintenance costs, etc.), this is a number, set to nil if not available -->
          <InntekterAndre-datadef-22101 orid="22101" xsi:nil="true" />
          <!--Element: Andre inntekter (Other income), this is a number, set to nil if not available -->
          <BruttoinntektUtleieMv-datadef-22033 orid="22033">232800</BruttoinntektUtleieMv-datadef-22033>
          <!--Element: Total income, this is a number. Add all incomes from above. In altinn this is auto generated -->
       </InntekterUtleieverdi-grp-960>
       <Kostnader-grp-236 gruppeid="236">
          <!-- Expenses (Kostnader) section -->
          <Festeavgift-grp-5281 gruppeid="5281">
             <!--Sub Section Party fee (basic rent), share of costs reported from housing association (Festeavgift (grunnleie)) section -->
             <Festeavgift-datadef-7885 orid="7885">1264</Festeavgift-datadef-7885>
             <!--Element: Total amount (including VAT) (Samlet beløp (medregnet mva.)), this is a number.  -->
             <FesteavgiftFradragsbrettiget-datadef-23634 orid="23634">1264</FesteavgiftFradragsbrettiget-datadef-23634>
             <!--Element: Deductible cost (Herav fradragsberettiget kostnad), this is a number.  -->
          </Festeavgift-grp-5281>
          <KommunaleAvgifter-grp-5282 gruppeid="5282">
             <!--Sub Section: Municipal fees (including any property tax) and insurance premiums for the property ( Kommunale avgifter (inkl. ev. eiendomsskatt) og forsikringspremier for eiendommen)  -->
             <AvgifterEiendomKommunale-datadef-7886 orid="7886">45245</AvgifterEiendomKommunale-datadef-7886>
             <!--Element: Total amount (including VAT) (Samlet beløp (medregnet mva.)), this is a number.  -->
             <AvgifterEiendomKommunaleFradragsberretiget-datadef-23635 orid="23635">45245</AvgifterEiendomKommunaleFradragsberretiget-datadef-23635>
             <!--Element: Deductible cost (Herav fradragsberettiget kostnad), this is a number.  -->
          </KommunaleAvgifter-grp-5282>
          <Lonnskostnader-grp-5283 gruppeid="5283">
             <!--Sub Section: Wages paid: ( Utbetalt lønn:)  -->
             <LonnsoppgaveInnsendt-datadef-7908 orid="7908">Nei</LonnsoppgaveInnsendt-datadef-7908>
             <!--Element: Is the amount reported to the Tax Administration? (Er beløpet innrapportert til Skatteetaten?), possible values ['Ja','Nei']  -->
             <DriftsutgifterVaktmesterBestyrerDisponentForretningsforer-datadef-7889 orid="7889">4000</DriftsutgifterVaktmesterBestyrerDisponentForretningsforer-datadef-7889>
             <!--Element: Total amount (including VAT) (Samlet beløp (medregnet mva.)), this is a number.  -->
             <DriftsutgifterVaktmesterBestyrerDisponentMvFradragsberretiget-datadef-23636 orid="23636">4000</DriftsutgifterVaktmesterBestyrerDisponentMvFradragsberretiget-datadef-23636>
             <!--Element: Deductible cost (Herav fradragsberettiget kostnad), this is a number.  -->
          </Lonnskostnader-grp-5283>
          <DriftsutgifterEiendomAvgifterLonnSkattemessig-datadef-23637 orid="23637">50509</DriftsutgifterEiendomAvgifterLonnSkattemessig-datadef-23637>
          <!--Element: Cost for deductions (Kostnader til fradrag), this is auto generated by adding all expenses in the expenses section -->
          <VedlikeholdPakostningerForandringerMv-grp-3488 gruppeid="3488">
             <!--Section: Maintenance (Vedlikehold)-->
             <VedlikeholdMv-grp-237 gruppeid="237">
                <!--Each group here represents a maintenance item -->
                <EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898 orid="7898">Materiell</EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898>
                <!--Element: What kind? (Hva slags?), just the name of the thing maintained -->
                <OppdragstakerNavnSpesifisertVedlikehold-datadef-7899 orid="7899">Oldernes Byggevare</OppdragstakerNavnSpesifisertVedlikehold-datadef-7899>
                <!--Element: The work is done by / the materials are provided by (Arbeidet er utført av/materialene er levert av ), who did the work-->
                <OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900 orid="7900">Postboks 383</OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900>
                <!--Element: Address (could be for the one who did the work ??) (Adresse)-->
                <OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901 orid="7901">9811</OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901>
                <!--Element: Zip code (Postnr)-->
                <OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902 orid="7902">Vadsø</OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902>
                <!--Element: City (Poststed) -->
                <EiendomVedlikeholdDatoSpesifisert-datadef-7903 orid="7903">2017-07-07</EiendomVedlikeholdDatoSpesifisert-datadef-7903>
                <!--Element: Date and Year (Dato og år) -->
                <DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904 orid="7904">3190</DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904>
                <!--Element: Total amount (Samlet beløp (medregnet mva)) -->
                <DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905 orid="7905">3190</DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905>
                <!--Element: Of which deductible cost (Herav fradragsberettiget vedlikehold). Seems like this is always the same as total cost -->
             </VedlikeholdMv-grp-237>
             <VedlikeholdMv-grp-237 gruppeid="237">
                <!--Another maintenance item -->
                <EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898 orid="7898">Vindu</EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898>
                <OppdragstakerNavnSpesifisertVedlikehold-datadef-7899 orid="7899">Grundes Byggshop AS</OppdragstakerNavnSpesifisertVedlikehold-datadef-7899>
                <OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900 orid="7900">Stoaveien 10</OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900>
                <OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901 orid="7901">4848</OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901>
                <OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902 orid="7902">Arendal</OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902>
                <EiendomVedlikeholdDatoSpesifisert-datadef-7903 orid="7903">2017-07-26</EiendomVedlikeholdDatoSpesifisert-datadef-7903>
                <DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904 orid="7904">43010</DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904>
                <DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905 orid="7905">43010</DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905>
             </VedlikeholdMv-grp-237>
             <VedlikeholdMv-grp-237 gruppeid="237">
                <EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898 orid="7898">Materiell</EiendomVedlikeholdBeskrivelseSpesifisert-datadef-7898>
                <OppdragstakerNavnSpesifisertVedlikehold-datadef-7899 orid="7899">Oldernes Byggevare</OppdragstakerNavnSpesifisertVedlikehold-datadef-7899>
                <OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900 orid="7900">Postboks 383</OppdragstakerAdresseSpesifisertVedlikehold-datadef-7900>
                <OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901 orid="7901">9811</OppdragstakerPostnummerSpesifisertVedlikehold-datadef-7901>
                <OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902 orid="7902">Vadsø</OppdragstakerPoststedSpesifisertVedlikehold-datadef-7902>
                <EiendomVedlikeholdDatoSpesifisert-datadef-7903 orid="7903">2017-07-28</EiendomVedlikeholdDatoSpesifisert-datadef-7903>
                <DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904 orid="7904">6702</DriftsutgifterEiendomSpesifisertVedlikeholdPakostningerMv-datadef-7904>
                <DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905 orid="7905">3351</DriftsutgifterEiendomVedlikeholdFradragsberettigetSpesifisert-datadef-7905>
             </VedlikeholdMv-grp-237>
             <DriftsutgifterEiendomVedlikeholdFradragsberettiget-datadef-7906 orid="7906">49551</DriftsutgifterEiendomVedlikeholdFradragsberettiget-datadef-7906>
             <!--Element: Sum of maintenance costs, this is auto generated by summing all deductible cost -->
             <DriftsutgifterEiendomVedlikeholdReduksjon-datadef-7907 orid="7907" xsi:nil="true" />
             <!--Element: Reduction when the residence has previously been exempted (Reduksjon når boligen tidligere har vært fritaksfastsatt), set to nil if empty -->
             <DriftsutgifterEiendomVedlikeholdSkattemessig-datadef-7890 orid="7890">49551</DriftsutgifterEiendomVedlikeholdSkattemessig-datadef-7890>
             <!--Element: Tota maintenance cost, that is, sum - reduction, this is auto generated -->
          </VedlikeholdPakostningerForandringerMv-grp-3488>
          <DriftsutgifterUtleieTap-datadef-7892 orid="7892" xsi:nil="true" />
          <!--Element:  Established loss of income from rental (Konstatert tap av inntekt ved utleie), set nil to true if empty -->
          <BygningUtleieAvskrivningBelop-datadef-22034 orid="22034" xsi:nil="true" />
          <!--Element:  Depreciation of building (Avskrivninger av bygning), set nil to true if empty -->
          <AndreKostnader-grp-971 gruppeid="971">
             <!-- Continues the expenses section: Other costs (specified), including depreciation of household goods (Andre kostnader (spesifisert), herunder avskrivninger av innbo). -->
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <!--Each group here represents a household good item -->
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Fryseskap</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <!--Element: Item Name-->
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">2199</DriftsutgifterAndreSpesifisert-datadef-10069>
                <!--Element: Amount (Beløp)-->
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <!--other items-->
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Snørydding</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">1438</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Strøm</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">35661</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Bredbåndskontrakt</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">1500</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Tv + internett</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">25476</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Fyringsved</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">2300</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Takst</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">4000</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <AndreKostnaderSpesifisert-grp-4944 gruppeid="4944">
                <DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894 orid="7894">Søppellevering</DriftsutgifterAndreBeskrivelseSpesifisert-datadef-7894>
                <DriftsutgifterAndreSpesifisert-datadef-10069 orid="10069">2400</DriftsutgifterAndreSpesifisert-datadef-10069>
             </AndreKostnaderSpesifisert-grp-4944>
             <DriftsutgifterLysBrenselRenholdEgenBoligdel-datadef-7896 orid="7896" xsi:nil="true" />
             <!--Element: Costs for own housing, electricity, heating, cleaning etc. (Kostnader til egen boligdel, strøm, oppvarming, renhold mv.), this is a number that has to be deducted if set-->
             <DriftsutgifterEgenBoligdel-datadef-22102 orid="22102">74974</DriftsutgifterEgenBoligdel-datadef-22102>
             <!--Element: Sum of all household goods, items and other costs after deducting from Costs for own housing-->
          </AndreKostnader-grp-971>
          <UtgifterFastEiendom-datadef-7918 orid="7918">175034</UtgifterFastEiendom-datadef-7918>
          <!--Element: Sum of all expenses, maintenance costs, household costs. This is auto generated taking info from expenses and maintenance section-->
       </Kostnader-grp-236>
       <Nettoinntekt-grp-4945 gruppeid="4945">
          <!--Section: Net Income (Nettoinntekt)-->
          <InntektNetto-datadef-28169 orid="28169">57766</InntektNetto-datadef-28169>
          <!--Element: Net income before any distribution to the spouse (Nettoinntekt før eventuell fordeling til ektefelle). This is calculated from Rental Income - Costs (maintenance + expenses + household). Auto generated -->
          <InntektOverfortEktefelle-datadef-28170 orid="28170">57766</InntektOverfortEktefelle-datadef-28170>
          <!--Element: Share of net income (profit / loss) transferred spouse. (Andel nettoinntekt (overskudd/underskudd) overført ektefelle.) -->
          <LeieinntekterNettoOverskudd-datadef-7897 orid="7897">0</LeieinntekterNettoOverskudd-datadef-7897>
          <!--Element: Surplus (Overskudd), auto calculated. Net - spouse-transfer; this is nil if net is negative -->
          <LeieinntekterNettoUnderskudd-datadef-14188 orid="14188" xsi:nil="true" />
          <!--Element: Deficit (Underskudd), autogen this should be set to the value if net was negative but without the negative sign, otherwise set to nil -->
       </Nettoinntekt-grp-4945>
       <Kontrollsporsmal-grp-239 gruppeid="239">
          <!--Section: Control Questions (Kontrollspørsmål) -->
          <OmfatterKostnadeneNoeAvFolgende-grp-2330 gruppeid="2330">
             <UtgifterSkattFormueInntekt-datadef-7911 orid="7911">Nei</UtgifterSkattFormueInntekt-datadef-7911>
             <!--Element:  Taxes on wealth and income (Skatter på formue og inntekt), possible values ['Ja','Nei'] -->
             <UtgifterSkatterFormueInntektBelop-datadef-7912 orid="7912" xsi:nil="true" />
             <!--Element:  Taxes on wealth and income value (Ev. beløp), if this was set to yes, a value must be filled here-->
             <UtgifterGodtgjoringHuseierMv-datadef-7913 orid="7913">Nei</UtgifterGodtgjoringHuseierMv-datadef-7913>
             <!--Element:  Remuneration of homeowners, spouses or children with joint determination of income and wealth (Godtgjørelse til huseier, ektefelle eller barn med felles fastsetting av inntekt og formue), possible values ['Ja','Nei'] -->
             <UtgifterGodtgjoringHuseierMvBelop-datadef-7914 orid="7914" xsi:nil="true" />
             <!--Element:  Remuneration of homeowners, spouses or children with joint determination of income and wealth (Godtgjørelse til huseier, ektefelle eller barn med felles fastsetting av inntekt og formue) Value if set to yes -->
             <UtgifterKontingentHuseierforeninger-datadef-7915 orid="7915">Nei</UtgifterKontingentHuseierforeninger-datadef-7915>
             <!--Element:  Contingent to homeowners' association or other associations (Kontingent til huseierforening eller andre foreninger), possible values ['Ja','Nei'] -->
             <UtgifterKontingentHuseierforeningerBelop-datadef-7916 orid="7916" xsi:nil="true" />
             <!--Element:  Contingent to homeowners' association or other associations (Kontingent til huseierforening eller andre foreninger), value if set to yes -->
          </OmfatterKostnadeneNoeAvFolgende-grp-2330>
       </Kontrollsporsmal-grp-239>
    </Skjema>

end