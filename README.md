# Hello_World
from pyrogram import Client, filters

# Replace with your values
api_id = 26890187  # Your Telegram API ID
api_hash = "216b90e73e67e0461b76a8358e14dbee"  # Your API hash from my.telegram.org
bot_token = "7552038900:AAF9MJnor0eyXhhMcOyHNAfDdXgLkA7f5x4"  # From BotFather
owner_id = 8175916316 # @radhe_5

# Your private channel's invite link
invite_link = "https://t.me/+zNZ_-Ra5ey5lODNl"

app = Client("invite_bot", api_id=,26890187 api_hash=216b90e73e67e0461b76a8358e14dbee, bot_token=7552038900:AAF9MJnor0eyXhhMcOyHNAfDdXgLkA7f5x4)

@app.on_message(filters.command("sendlink") & filters.user(owner_id))
async def send_invite(client, message):
    if len(message.command) < 2:
        await message.reply("❗ Use: /sendlink @username")
        return

    username = message.command[1]
    if not username.startswith("@"):  # Validate username format
        await message.reply("❗ Username must start with @")
        return

    try:
        await client.send_message(username, f"🔗 Here is your private channel invite link: {invite_link}")
        await message.reply(f"✅ Invite link sent to {username}")
    except Exception as e:
        await message.reply(f"❌ Failed to send link: {e}") control+shift +m 1
        
        
