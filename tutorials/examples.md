---
order: 50
--- 
 ##   Prefix Command: 
First a hello command that gives some very basic info:
```py
@bot.command()
async def Hello(ctx):
    member = ctx.author
    roles = []
    for role in member.roles[1:]:
        roles.append(role.name)
    role_names = ', '.join(roles)
    message = f"Hello {member.name}! You are a {role_names} in this server."
    await ctx.send(message)
```
In this implementation, we define a function named Hello using the `@bot.command()` decorator. The function takes a single parameter named ctx, which represents the context of the message that triggered the command.

1. Define the `Hello` command using the `@bot.command()` decorator, where bot is an instance of the `discord.Bot()` class or `discord.ext.commands.Bot()` class (for most use cases the same).
2. In the function that implements the Hello command, use the ctx parameter to access the context of the message that triggered the command. The context contains information about the channel, server, and user who sent the message.
3. Use the `ctx.author` attribute to get the `discord.Member` object that represents the user who sent the message. The `discord.Member` object contains information about the user's roles, nickname, status, and more.
4. (Use the `ctx.channel` attribute to get the `discord.TextChannel` object that represents the channel where the message was sent.)
5. Use the await `ctx.send()` method to send a message to the channel where the command was triggered. You can use this method to format the message.


 ##    Slash Commands:
### Dice roll
```py
@bot.tree.command(name="dice",description="A command to roll x number of dice")
async def dice(interaction : discord.Interaction, amount : int =1):
    rolls = []
    for i in range range(0, int(amount):
        rolls.append(random.randint(0, 6))
    message = "You rolled: " + ', '.join(rolls) + '\n' +
                "Total sum is: " + str(sum(rolls))
    await interaction.response.send_message()
``` 
###  Nickname
```py
@bot.tree.command(name="nickname", description="change someone's nickname")
@commands.has_guild_permissions(manage_nicknames=True)
@commands.bot_has_guild_permissions(manage_nicknames=True)
async def nickname(interaction: discord.Interaction, member: discord.Member, nickname: str):
    await member.edit(nick=nickname)
    await member.send("Your nickname has been changed!")
```
### send message
```py
@bot.tree.command(name="send", description="send message to specific channel")
async def send_message(interaction: discord.Interaction, channel: discord.TextChannel, message: str):
    await channel.send(message)
    await interaction.response.send_message("Message sent!")
```

 ## Embeds
 Embeds are a way to display your messages in a nice way.
 You make a discord.embed Object and can set the various fields, these can be found in the docs: 
[https://discordpy.readthedocs.io/en/latest/api.html#discord.Embed](https://discordpy.readthedocs.io/en/latest/api.html#discord.Embed)
```py
@bot.tree.command(name="serverinfo", description="Get some useful (or not) information about the server.")
async def serverinfo(interaction: discord.Interaction) -> None:
    roles = [f"<@&{role.id}>" for role in interaction.guild.roles]
    if len(roles) > 50:
        roles = roles[:50]
        roles.append(f">>>> Displaying[50/{len(roles)}] Roles")
    roles = ", ".join(roles)

    embed = discord.Embed(
        title="**Server Name:**", description=f"{interaction.guild}", color=0x9C84EF
    )
    if interaction.guild.icon is not None:
        embed.set_thumbnail(url=interaction.guild.icon.url)
    embed.add_field(name="Server ID", value=interaction.guild.id)
    embed.add_field(name="Member Count", value=interaction.guild.member_count)
    embed.add_field(
        name="Text/Voice Channels", value=f"{len(interaction.guild.channels)}"
    )
    embed.add_field(name=f"Roles ({len(interaction.guild.roles)})", value=roles)
    embed.set_footer(text=f"Created at: {interaction.guild.created_at}")
    await interaction.response.send_message(embed=embed)
```
    
 ## Button, SelectMenu (Dropdown)
    Voorbeeld dropdown & selectMenu
    
 ## Webrequests
    Voorbeelden webrequests
        