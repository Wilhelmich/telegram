import random
import asyncio
from telethon import TelegramClient
from telethon.tl.functions.messages import SendMessageRequest
from config import API_id, API_hash

# Replace YOUR_API_ID and YOUR_API_HASH with your API ID and API hash
api_id = API_id
api_hash = API_hash

# Replace YOUR_CHANNEL_USERNAME with the target channel username (with @ symbol)
channel_username = '@[ username channel ] '

# Replace YOUR_MESSAGE with your message
message = '  YOUR MESMESSAGES  '


# Define the minimum and maximum interval in seconds between message sends
min_interval = 4540
max_interval = 7200

async def send_message():
    # Create a Telegram client with your API ID and API hash
    async with TelegramClient('session_name', api_id, api_hash) as client:
        # Connect to the Telegram server and log in as a user
        await client.start()

        # Send the message to the target channel
        response = await client(SendMessageRequest(
            peer=channel_username,
            message=message
        ))

        # Disconnect from the Telegram server
        await client.disconnect()

# Schedule the send_message function to run every random interval between min_interval and max_interval seconds
async def schedule_message():
    while True:
        await send_message()
        print("gesendet")
        # Generate a new random interval for the next message
        interval = random.randint(5400, 7200)
        await asyncio.sleep(interval)

# Run the schedule_message function
asyncio.run(schedule_message())
# Run the schedule_message function
asyncio.run(schedule_message())
