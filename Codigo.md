import discord
import random
import os

print(os.listdir('memes'))

from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Hola, soy un bot {bot.user}!')

@bot.command()
async def heh(ctx, count_heh = 100):
    await ctx.send("he" * count_heh)


@bot.command()
async def mem(ctx):
    imagenes = os.listdir("memes")
    with open(f'memes/{random.choice(imagenes)}', 'rb') as f:
            picture = discord.File
    await ctx.send(file=picture)
@bot.command()
async def contaminacion(ctx):
    await ctx.send(f"""Hola, soy un bot {bot.user}!""")# esta linea saluda
    await ctx.send(f'Te voy hablar un poco sobre la contaminacion')
    await ctx.send(f'La contaminación es un gran problema a nivel mundial, muchos paises sufren a diario')
    # Enviar una pregunta al usuario
    await ctx.send("Quieres consejos sobre cómo combatir la contaminación? Responde con 'sí' o 'no'.")
# Esperar la respuesta del usuario
    def check(message):
        return message.author == ctx.author and message.channel == ctx.channel and message.content in ['sí', 'si', 'no']
    response = await bot.wait_for('message', check=check)
    if response:
        if response.content in ['sí', 'si']:
            await ctx.send("1. No arrojar basura en los rios")
            await ctx.send("2. Dejar de quemar basuras")   
        else:
            await ctx.send("Está bien, si alguna vez necesitas consejos, no dudes en preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
    await ctx.send("Quieres saber la definicion de contaminacion, responde si o no")
    response1 = await bot.wait_for('message', check=check)
    if response1:
        if response1.content in ['sí', 'si']:
            await ctx.send("Arrojar basura") 
        else:
            await ctx.send("Está bien, si alguna vez necesitas consejos, no dudes en preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
           



@bot.command()
async def videojuegos(ctx):
    await ctx.send(f"""Hola, soy un bot {bot.user}!""")# esta linea saluda
    await ctx.send(f'Te voy hablar un poco sobre los videojuegos')
    await ctx.send(f'Los videojuegos han cambiado el mundo por completo te voy a contar varios datos curiosos')
    # Enviar una pregunta al usuario
    await ctx.send("Quieres saberlos? Responde con 'sí' o 'no'.")
# Esperar la respuesta del usuario
    def check(message):
        return message.author == ctx.author and message.channel == ctx.channel and message.content in ['sí', 'si', 'no']
    response = await bot.wait_for('message', check=check)
    if response:
        if response.content in ['sí', 'si']:
            await ctx.send("1. El primer videojuego del mundo se llama OXO es como ping pong ")
            await ctx.send("2. El juego mas vendido en la historia es el Tetris con mas de 520 millones de compras")   
            await ctx.send("3. El año en el que se crearon los videojuegos fue el 1952")
        else:
            await ctx.send("Está bien, Si necesitas saber no te olvides de preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
    await ctx.send("Quieres saber la definicion de videojuego, responde si o no")
    response1 = await bot.wait_for('message', check=check)
    if response1:
        if response1.content in ['sí', 'si']:
            await ctx.send("Los videojuegos se definen como un programa que se ocupa para el entretenimiento") 
        else:
            await ctx.send("Está bien, si alguna vez necesitas curiosidades de los videojuegos , no dudes en preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
@bot.command()
async def idiomas(ctx):
    await ctx.send(f"""Hola, soy un bot {bot.user}!""")# esta linea saluda
    await ctx.send(f'Te voy a hablar sobre los idiomas')
    await ctx.send(f'Los idiomas nos ayudan a viajar te voy a dar consejos de como aprenderlos ')
    # Enviar una pregunta al usuario
    await ctx.send("Quieres saber? Responde con 'sí' o 'no'.")
# Esperar la respuesta del usuario
    def check(message):
        return message.author == ctx.author and message.channel == ctx.channel and message.content in ['sí', 'si', 'no']
    response = await bot.wait_for('message', check=check)
    if response:
        if response.content in ['sí', 'si']:
            await ctx.send("1. Si tu quieres aprender idiomas y te gustan los videojuegos un consejo es que cambias el idioma del juego y ponla en el idioma que tu quieras aprender")
            await ctx.send("2. Intenta practicar tu idioma escuchando musica en el idioma que quieras aprender")   
            await ctx.send("3. Y por ultimo investiga cosas relacionadas con el idioma y si te gusta leer intenta leer libros en otros idiomas")
        else:
            await ctx.send("Está bien, Si necesitas saber no te olvides de preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
    await ctx.send("Quieres saber la definicion de idioma?, responde si o no")
    response1 = await bot.wait_for('message', check=check)
    if response1:
        if response1.content in ['sí', 'si']:
            await ctx.send("Los idiomas se definen como lenguas que se hablan en lugares especificos") 
        else:
            await ctx.send("Está bien, si alguna vez necesitas consejos de los idiomas , no dudes en preguntar.")
    else:
        await ctx.send("Lo siento, no pude entender tu respuesta. Inténtalo de nuevo.")
bot.run("TOKEN")
