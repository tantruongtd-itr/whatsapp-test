# About Twilio

Twilio is a third party service that provides APIs to send messages with Whatsapp.

> [!NOTE]
> Twilio doesn't provide verify on-Whatsapp phone number but we can work around by trigger sendMessage API then parse the response to get .

## Requisites

* Create a Twilio account [here](https://login.twilio.com/u/signup).

* Connect a WhatsApp number to the Twilio account.

* Obtain the account 's Whatsapp API key.

## API

Sample send message JS code:

```js
const accountSid = `${someRandomString}`;
const authToken = `${someRandomString}`;
const client = require('twilio')(accountSid, authToken);

client.messages
    .create({
        body: 'Your appointment is coming up on July 21 at 3PM',
        from: 'whatsapp:+14155238886',
        to: 'whatsapp:+84898393452'
    })
    .then(message => console.log(message.sid))
    .done();
```

Sample response:

```js
// 201 - CREATED - The request was successful. We created a new resource and the response body contains the representation.
{
  "api_version": "",
  "body": "Your appointment is coming up on July 21 at 3PM",
  "date_created": "Thu, 06 Jun 2024 08:35:40 +0000",
  "date_sent": null,
  "date_updated": "Thu, 06 Jun 2024 08:35:40 +0000",
  "direction": "outbound-api",
  "error_code": null,
  "error_message": null,
  "from": "whatsapp:+14155238886",
  "messaging_service_sid": null,
  "num_media": "0",
  "num_segments": "1",
  "price": null,
  "price_unit": null,
  "sid": "someRandomStringSId",
  "status": "queued",
  "subresource_uris": {
    "media": "..."
  },
  "to": "whatsapp:+84123456789",
  "uri": "..."
}
```

## Fee

Conversations-Based Pricing + Message-Based Pricing [link](https://www.twilio.com/en-us/whatsapp/pricing)

In North America: $0.015/Conversation, $0.005/Message

> [!NOTE]
> In our case, an alert per patient on what-apps will cost $0.02 as a conversation will be initiated every 24h.
> Twilio doesn't charge on failed message (not on what-apps patient) so we could save money on those patients.
