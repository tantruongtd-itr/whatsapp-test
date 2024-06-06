# WhatsApp Business Platform

There is another way to do those step using Whatsapp business platform cloud API

> [!NOTE]
> On-premise is another option for Whatsapp business platform but it is not as convenient and we need additional fee for maintaining hosting server to manage them.

## Requisites

* Create a Meta business profile [here](https://www.facebook.com/business).

* Connect a WhatsApp number to the profile.

* Obtain the account 's Whatsapp API key.

## API

As far as I see, currently Whatsapp doesn't support API to verify number exists maybe there 's a work around by:

* Trigger send message API [document here](https://developers.facebook.com/docs/whatsapp/cloud-api/reference/messages#text-messages)
* Listen the response using webhook and check if message is successfully sent.

## Fee

Conversations-Based Pricing [link](https://scontent.fsgn5-15.fna.fbcdn.net/v/t39.8562-6/350685135_631521772182777_716278591301876804_n.pdf?_nc_cat=111&ccb=1-7&_nc_sid=b8d81d&_nc_ohc=q45Ei2MXBNcQ7kNvgGQ1R-n&_nc_ht=scontent.fsgn5-15.fna&oh=00_AYBU8KvdYS2xSmoWY_obkXX5R7dYeclm_EDGg_oqk2TEtg&oe=66647990)

A conversation will last for 24 hours when first initiated (first message sent) no cost for the message.

First 1000 conversations per month is free across all of business phone numbers.

Rate for Service in North America: 0.0088 / Service
s