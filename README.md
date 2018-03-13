# nagios-telegram-notification
Nagios host and service notifications via Telegram bot

# Create a Telegram bot
Message @BotFather in your Telegram app. Write down your bots access token, which is something like '53355511:AaFnF2Xnt1-RjGMaQZ_412tvp-_e12312KQ'. When using the token, you add 'bot' in-front of the token to complete it, turning the access token into 'bot53355511:AaFnF2Xnt1-RjGMaQZ_412tvp-_e12312KQ'.

Next, type /setprivacy to @BotFather and set DISABLE for your bot.

# Invite the bot to your Telegram group
Select 'Info' on your group name in your Telegram app and invite the bot. Make sure you are admin of the group or there may be issues.

# Write something in the Telegram group
As yourself, write something in the group.

# Fetch the chat_id of the Telegram group
Fetch events from your bot by running:
````
curl -Lk -i -X GET https://api.telegram.org/botACCESSTOKEN-GIVEN-FROM-BOTFATHER/getUpdates
````
Output will be something like:
````
"message":{"message_id":14,"from":{"id":300920731,"is_bot":false,"first_name":"Your","last_name":"Name","language_code":"en-US"},"chat":{"id":-123456789,"title":"My fancy Telegram group","type":"supergroup"},"date":1520901132,"text":"I like beer"}}]}
````
Copy and save "chat" id, which in above example is -123456789.

# Copy custom notification commands
Copy the custom notifications commands from here: https://github.com/mglantz/nagios-telegram-notification/blob/master/command.cfg and replace the chat_id value with above and replace botREPLACEME with your full access token.


