---
title: GetAuthenticationChallenge
date: 2020-03-13
slug: get-authentication-challenge

---
This is used to authenticate the user with Altinn. The users receive an SMS pin that is then used for subsequent request to other endpoints.

### Authentication Methods

When users login through Altinn they get to choose from several possible types of login as shown below:

![](/Screenshot 2020-03-15 at 7.47.16 PM.png)

When authenticating through SOAP we need to specify the method. Altinn only supports authentication through MINID. Both AltinnPin and SMSPin refer to the MINID. 

In production, we will be using SMSPin so users get the pin through SMS. However, we _might_ give them an option to use a physical pin if they ordered so which will then use AltinnPin. This method needs to be investigated for production scenario.

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

This will result indicating which PIN code (from date of letter) the user to use. This PIN code is through a letter sent to the user. In such letter, users usually have multiple pins and therefore the response is something like:

> Benytt engangskode 8 fra brev datert torsdag, 17. desember 2015

We might not use this method in production.

Each authentication is only valid for 30 mins of inactivity.

**Response Example:**

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

#### SMSPin

This seems to be the correct method to use to send an SMS to the user which we can use. AltinnPin above seems to be a pin code retrieved through a letter. All parameters are same except for AuthMethod which will be set to SMSPin

If no phone number is found, we get an error.

    <s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
       <s:Body>
          <GetAuthenticationChallengeResponse xmlns="http://www.altinn.no/services/Authentication/SystemAuthentication/2009/10">
             <GetAuthenticationChallengeResult xmlns:a="http://schemas.altinn.no/services/Authentication/2009/10" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <a:Message>Mobilnummer er ikke registrert på bruker. Registrer mobilnummer i Min profil på altinn.no</a:Message>
                <a:Status>NoPhoneNumber</a:Status>
                <a:ValidFrom>0001-01-01T00:00:00</a:ValidFrom>
                <a:ValidTo>0001-01-01T00:00:00</a:ValidTo>
             </GetAuthenticationChallengeResult>
          </GetAuthenticationChallengeResponse>
       </s:Body>
    </s:Envelope>

end