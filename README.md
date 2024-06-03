# WhatsApp number checker and send message

This project uses [2Chat's](https://2chat.co?ref=gh) public API to demonstrate steps to verify if a given phone number has a WhatsApp account then send `hello world!` message.

> [!TIP]
> The script defaults to waiting 5 seconds between each check to prevent being throttled by the API. If you have a paid subscription with 2Chat, you can lower this value to 1 second.

## Requisites

* Create a 2Chat account [here](https://app.2chat.io/signup).

* Connect a WhatsApp number connected to the account [here](https://help.2chat.io/en/articles/7243195-how-to-create-a-whatsapp-channel?ref=gh).

* Obtain the account 's 2Chat API key [here](https://help.2chat.io/en/articles/7830948-where-you-can-find-the-api-code-in-2chat?ref=gh).

## How to set up and run

This is a Node script written in Javascript.

To run it, clone this repository and:

* Create a file named `.env` with your API key in it:

```text
API_KEY=<your API key here>
```

* Create a file with the numbers you want to check. For example, `my-numbers-to-check.csv` and use the following format:

```text
  +17137157533
```

* Call the script with the configured parameters:

`--number` must be the number you connected to your 2Chat account. For example, `+17137157533`.

```bash
  node check-number.js --in=my-numbers-to-check.csv --out=example-output.csv --number=+17137157533
```

## API limits and running this script in parallel

We recommend you run a single instance of this script for every connected number on your 2Chat account to achieve faster speeds.

## Billing

* Your account may be rate-limited during the trial period.
* Upgrade to enhance request limit [here](https://app.2chat.io/billing?).
