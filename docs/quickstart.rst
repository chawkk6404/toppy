Quickstart
===========

Installation
--------------
**Python 3.8 or higher is needed**

.. code:: sh

    $ pip install -U toppy-python



Example
---------

.. code:: py

    import toppy
    import aiohttp
    from discord.ext import commands
    

    dbl_token = 'Your Discord Bot List token here'
    topgg_token = 'your Top.gg token here'
    
    bot = commands.Bot('!')  # or discord.Client()
    toppy_client = toppy.Client(
        bot, dbl_token=dbl_token,
        topgg_token=topgg_token
    )
    
    
    @bot.event
    async def on_dbl_autopost_success():  # dbl/dbgg/topgg
        print('Server count posted')
        print(f'Server count: {len(bot.guilds)}')
    

    @bot.event
    async def on_dbl_autopost_error(error: toppy.ClientResponseError):  # dbl/dbgg/topgg
        print(f'Uh oh. An error occurred: {error.message}')
       
    
    
    bot.run(...)
