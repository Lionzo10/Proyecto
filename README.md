# Proyecto
import discord


# La variable intents almacena los privilegios del bot
intents = discord.Intents.default()
# Activar el privilegio de lectura de mensajes
intents.message_content = True
# Crear un bot en la variable cliente y transferirle los privilegios
client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print(f'Hemos iniciado sesión como {client.user}')

@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('$hola'):
        await message.channel.send("Buenas :V")
    elif message.content.startswith('$bye'):
        await message.channel.send("chau papu")
    elif message.content.startswith("$Como estas"):
        await message.channel.send("bien y tu?")
    elif message.content.startswith("$help"):
        await message.channel.send("Hola soy un bot de ideas de reciclaje solo pon $ y lo que quieras hacer y te ayudare ")
    elif message.content.startswith("$Maceta"):
        await message.channel.send("claro para hacer una maceta se necesita: 1.- cortar la parte de arriba de una botella 2.- decora la maceta a tu gusto(opcional) 3.- haces un hoyo en la parte de abajo y pones la parte de arriba en el hoyo 4.- pues ya esta listo :V")
    elif message.content.startswith("$Avión"):
        await message.channel.send("Pues con una hoja reciclada haces un avión de papel ($como hacer avión de papel)")
    elif message.content.startswith("$como hacer un avión de papel"):
        await message.channel.send("apoco no sabes? bueno pues: 1.- agarra una hoja 2.-doblala a la mitad 3.-doblas una esquina 4.-el 3 pero con la otra 5.-doblas la esquina de nuevo 6.- la 5 pero con la otra 7.- lo doblas a la mitad 8.- ya tienes un avión de papel :D")
    elif message.content.startswith("$Naranja"):
        await message.channel.send("Para plantar una naranja te mando este video espero que te sirva (https://www.youtube.com/watch?v=Sg2OFOndJOQ)")
    elif message.content.startswith("$Agua"):
        await message.channel.send("Para ahorrar agua tienes que: 1.- bañarte en 5 o menos minutos 2.- no dejar el grifo abierto 3.- arrglar figas de agua 4.-no comprar tanta ropa 5.- no comer tanta carne 6.- no tirar el agua ")
    elif message.content.startswith("$Botes de reciclaje"):
        await message.channel.send("Gris: Desechos en General, Naranja: Organicos, Verde: Envases de vidrio, Amarillo: Plasticos y envases metalicos, Azul: Papel, Rojo: Hospitalarios infecciosos")
    else:
        await message.channel.send("No se como hacer eso :V")



client.run("")
