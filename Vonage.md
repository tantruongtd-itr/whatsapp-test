# About Vonage

Vonage is a third party service that provides APIs to send messages with Whatsapp.

> [!NOTE]
> Vonage doesn't provide verify on-Whatsapp phone number but we can work around by trigger sendMessage API then parse the response got from its webhooks.
> Detail [here](https://api.support.vonage.com/hc/en-us/articles/4678328740116-Do-you-have-an-API-to-check-if-the-user-is-WhatsApp-enabled)

## Requisites

* Create a Vonage account [here](https://ui.idp.vonage.com/ui/auth/registration).

* Connect a WhatsApp number to the Vonage account.

* Obtain the account 's Vonage API key.

## API

Sample send message JS code:

```bash
curl -X POST https://messages-sandbox.nexmo.com/v1/messages \
-u 'VonageAPIKey' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-d '{
    "from": "14157386102",
    "to": "84123456789",
    "message_type": "text",
    "text": "This is a WhatsApp Message sent from the Messages API",
    "channel": "whatsapp"
  }'
```

## Fee

Conversations-Based Pricing [link](https://www.vonage.com/communications-apis/messages/pricing/)

In North America: $0.0488 USD/Conversation doesn't care category.

> [!NOTE]
> Don't charged in case of failed messages.
