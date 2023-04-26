---
order: 70
---

## Basic use

Decorators in Python are a design pattern that allows you to modify the functionality of a function by wrapping it in another function. In other words, a decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it. The outer function is called the decorator, which takes the original function as an argument and returns a modified version of it.

In the context of a Python Discord bot, decorators can be useful for modifying the behavior of functions that are called when specific events happen, such as when a message is received or when a user joins the server. For example, a decorator can be used to check if the user sending a message is authorized to use a specific command before allowing the command to execute.

These decorators are used for different types of commands, permissions checking or modifiers.
Examples of these decorators are as follows and work by adding them to any function.

```py
    @bot.event()
    @bot.command()
    @bot.command(aliases=["com1", "com-1"])
    @bot.tree.command(name, description)
    @bot.hybrid_command(name, description)
    @tasks.loop(minutes=1.0)
    @commands.cooldown(rate, seconds)
    @commands.dm_only()
    @commands.is_owner()
    @commands.has_role()
    @commands.dm_only()
```
More can be found in the docs: [https://discordpy.readthedocs.io/en/stable/ext/commands/api.html?highlight=decorator#decorators](https://discordpy.readthedocs.io/en/stable/ext/commands/api.html?highlight=decorator#decorators)
## Inner workings

To go more in depth into decorators, there are a few important concepts related to Python functions that need to be understood. In Python, everything is an object, including functions. A function returns a value based on the given arguments. Functions in Python may also have side effects rather than just turning an input into an output. For example, the print() function is a basic example of a function that has a side effect of outputting something to the console.

To create a decorator, a few building blocks are used. First, a function is defined that takes another function as an argument. Then, a new function is defined inside the first function that calls the original function and modifies its behavior in some way. Finally, the new function is returned. Here is an example of a decorator in action:

```py
def my_decorator(original_function):
    def new_function():
        print("Before the original function is called.")
        original_function()
        print("After the original function is called.")
    return new_function

@my_decorator
def my_function():
    print("Inside the original function.")

my_function()
```

When the `my_function()` is called, it is wrapped by the `my_decorator()` function, which modifies its behavior by printing "Before the original function is called." before the original function is called and "After the original function is called." after the original function is called.

Decorators can be used for a variety of purposes, such as adding logging, testing performance, performing caching, verifying permissions, and more. Decorators can also be used to run the same code on multiple functions, which avoids writing duplicating code.

In summary, decorators in Python are a powerful tool that allows programmers to modify the behavior of functions or classes without modifying the existing structure. They can be used in a variety of contexts, including Python Discord bots, to modify the behavior of functions that are called when specific events happen. However, it is important to understand how functions work in Python before diving into decorators. While decorators are a useful tool for wrapping code around defined blocks, debugging can become challenging when multiple decorators are used on a single function.