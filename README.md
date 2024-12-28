from telegram.ext import Updater, CommandHandler

# Function to handle the /start command
def start(update, context):
    update.message.reply_text("Welcome! I am your bot.")

# Main function to start the bot
def main():
    TOKEN = "YOUR_BOT_TOKEN"  # Replace with your bot token
    updater = Updater(token=TOKEN, use_context=True)
    dispatcher = updater.dispatcher

    # Command handler for /start
    start_handler = CommandHandler("start", start)
    dispatcher.add_handler(start_handler)

    # Start the bot
    updater.start_polling()
    updater.idle()

if __name__ == "__main__":
    main()
