---
label: "Running your app"
icon: play
---

## Adding credentials
There's already some code in your `bot.py` file, but you'll need your app's token and ID to make requests. All of your credentials can be stored directly in the `config.json` file.

First, copy your bot user's token from earlier and paste it in the `prefix` field.

Next, navigate to your app's General Overview page, then copy the App ID and Public Key. Paste the values into the file as `application_id` and `public_key`.
```json
{
    "prefix": "YOUR_BOT_PREFIX_HERE",
    "token": "YOUR_BOT_TOKEN_HERE",
    "permissions": "YOUR_BOT_PERMISSIONS_HERE",
    "application_id": "YOUR_APPLICATION_ID_HERE",
    "public_key": "YOUR_PUBLIC_KEY_HERE"
}
```

## Running bot
You can now run the bot using your IDE or CLI interface like you would run any other python program.

`python bot.py`