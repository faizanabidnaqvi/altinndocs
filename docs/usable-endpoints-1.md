---
title: GetAuthenticationChallenge
date: 2020-03-13
slug: GetAuthenticationChallenge

---
This is used to authenticate the user with Altinn. The users receive an SMS pin that is then used for subsequent request to other endpoints.

### Authentication Methods

When users login through Altinn they get to choose from several possible types of login as shown below:

![](/Screenshot 2020-03-15 at 7.47.16 PM.png)

When authenticating through SOAP we need to specify the method. Methods correspond to one of the above.

#### AltinnPin

This corresponds to the "MINIID" type in the authentication portal. The inputs are:

UserSSN: The social security number for the user. It is important to NEVER save this in the database.

UserPassword: The password used for MINID. Similar to SSN, this should NEVER be saved in the database.

**Request Example**

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://www.altinn.no/services/Authentication/SystemAuthentication/2009/10" xmlns:ns1="http://schemas.altinn.no/services/Authentication/2009/10">
       <soapenv:Header/>
       <soapenv:Body>
          <ns:GetAuthenticationChallenge>
             <ns:challengeRequest>
                <ns1:AuthMethod>AltinnPin</ns1:AuthMethod>
                <ns1:UserPassword>password01</ns1:UserPassword>
                <ns1:UserSSN>30014500525</ns1:UserSSN>
             </ns:challengeRequest>
          </ns:GetAuthenticationChallenge>
       </soapenv:Body>
    </soapenv:Envelope>

This will result in sending an SMS to the user which is valid for 20 mins (recheck) of inactivity. The SMS will be used for all subsequent authentication for the user.

Response Example:

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <GetAuthenticationChallengeResponse xmlns="http://www.altinn.no/services/Authentication/SystemAuthentication/2009/10">
             <GetAuthenticationChallengeResult xmlns:a="http://schemas.altinn.no/services/Authentication/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:Message>Benytt engangskode 2 fra brev datert torsdag, 17. desember 2015</a:Message>
                <a:Status>Ok</a:Status>
                <a:ValidFrom>2020-03-15T13:00:44.2353668+01:00</a:ValidFrom>
                <a:ValidTo>2020-03-15T13:30:44.2353668+01:00</a:ValidTo>
             </GetAuthenticationChallengeResult>
          </GetAuthenticationChallengeResponse>
       </s:Body>
    </s:Envelope>