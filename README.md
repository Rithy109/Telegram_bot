# Telegram_bot
Telegram_bot
from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext

# Define a function that will handle the /start command
def start(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('Hello, World!')

def main():
    # Replace 'YOUR_TOKEN' with your actual bot token
    updater = Updater("YOUR_TOKEN")

    # Get the dispatcher to register handlers
    dispatcher = updater.dispatcher

    # Register the /start command handler
    dispatcher.add_handler(CommandHandler("start", start))

    # Start the Bot
    updater.start_polling()

    # Run the bot until you send a signal to stop
    updater.idle()

if __name__ == '__main__':
    main()
