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
    "prefix": "BOT_PREFIX",
    "token": "BOT_TOKEN",
    "permissions": "BOT_PERMISSIONS",
    "application_id": "APPLICATION_ID",
    "public_key": "PUBLIC_KEY"
}
```

## Running bot
You can now run the bot using your IDE or CLI interface like you would run any other python program.

`python bot.py`