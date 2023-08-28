# Geeks_MedBot_Aviothic1.0
MedBot is an AI Powerd(ChatGPT3.5) ChatBot ,it is designed to answer various questions and it is also avails Diet Planning and Stress Management And it Also Send You Daily Motivational Quotes to Boost your Metal Health
Telegram Bot UserName:   http://t.me/medaiop_bot
import os
import telegram
import openai

# Set up OpenAI API
openai.api_key = '***********************************D8hOaFKw'

# Set up Telegram bot
bot = telegram.Bot(token='**************************8DDPay6iBMk')

def lambda_handler(event, context):
    # Extract the message content from the Telegram update
    update = telegram.Update.de_json(event['body'], bot)
    message = update.message
    chat_id = message.chat_id
    text = message.text

   Send the message to OpenAI API for processing
    response = openai.Completion.create(
        engine='davinci-codex',  # Choose the appropriate OpenAI engine
        prompt=text,
        max_tokens=50  # Adjust the response length as needed
    )

   # Extract the generated message from OpenAI response
   generated_message = response.choices[0].text.strip()

   # Send the generated message back to the Telegram chat
   bot.send_message(chat_id=chat_id, text=generated_message)
    
# Functions of MedBot:
1-The Ultimate Q&A Partner: Got questions? MedBot has answers! With the help of its trusty sidekick

2-Motivational Messaging: MedBot kicks off each conversation with a motivational message

3-Stress Management Techniques: MedBot has access to a treasure trove of research-based stress management techniques.

4-Personalized Diet Plans: Picture this: MedBot becomes your very own culinary wizard, helping you create diet plans tailored to your preferences and goals.

