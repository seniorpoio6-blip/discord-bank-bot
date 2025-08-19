import discord
from discord.ext import commands

# ⚠️ Pega aquí tu token del bot de Discord
TOKEN = "AQUI_TU_TOKEN"

# Configuramos los intents (necesarios para que el bot lea mensajes)
intents = discord.Intents.default()
intents.message_content = True  

# Prefijo de comandos, por ejemplo: !ping
bot = commands.Bot(command_prefix="!", intents=intents)

# Evento al iniciar el bot
@bot.event
async def on_ready():
    print(f"✅ Bot conectado como {bot.user}")

# Comando básico de prueba
@bot.command()
async def ping(ctx):
    await ctx.send("pong 🏓")

# Arrancar el bot
bot.run(TOKEN)
