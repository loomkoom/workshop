---
order: 100
---

```py
import discord
from discord.ext import commands
from discord.ext.commands import Bot

TOKEN = 'TOKEN HERE'

intents = discord.Intents.default()
# message content for prefix commands
intents.message_content = True

bot = Bot(command_prefix="$ab", intents=intents)

@bot.event
async def on_ready() -> None:
    """
    The code in this event is executed when the bot is ready.
    """
    channel = bot.get_channel(12324234183172)
    await channel.send(f"Bot logged in as {bot.user.name}")


bot.run(TOKEN)
```