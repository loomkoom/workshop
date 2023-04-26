---
order: 80
---

Event-driven programming is a programming paradigm where the flow of a program is determined by events such as user actions, sensor outputs, or message passing from other programs or threads. In an event-driven application, there is generally a main loop that listens for events and then triggers a callback function when one of those events is detected.
In very simple terms the code you write is as folllows.

```python
#client
While True
    async listen_to_event()
    # async -> can run whenever
    # await  -> wneeds to wait for value until it continues

run_event_loop()


#server
do_stuff()
send_event()
do_stuff()
...

```

To create an event-driven program, the first step is to write a series of subroutines, or methods, called event-handler routines that handle the events to which the main program will respond. In discord.py these are created using `@bot.event`.

For a Discord bot, the event loop would listen for events in the Discord server and execute the corresponding event handlers. Some examples of events in a Discord bot are a user joining a server, a user sending a message, or a user reacting to a message. The event handler for a user sending a message could be a function that takes the message as an input, processes it, and sends a response back to the server. The event handler for a user reacting to a message could be a function that adds a reaction to the message or performs some other action.
A full list of events can be found here: [https://discordpy.readthedocs.io/en/stable/api.html#event-reference](https://discordpy.readthedocs.io/en/stable/api.html#event-reference) 

The most common ones can be seen below.
```
on_ready, 
on_message, 
on_message_edit, 
on_guild_join, 
on_member_ban, 
on_user_update, 
on_reaction_add, 
on_voice_state_update
```