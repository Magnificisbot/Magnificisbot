#!/usr/bin/python

# This is a simple echo bot using the decorator mechanism.
# It echoes any incoming text messages.

import telebot

API_TOKEN = '5092281641:AAFbWdZ6QUnWUT4ktzn2JEVSulEycIIyd68'

bot = telebot.TeleBot(API_TOKEN)


# Handle '/start' and '/help'
@bot.message_handler(commands=['help', 'start'])
def send_welcome(message):
    bot.reply_to(message, """\
Salve, questo è il bot delle Aste di OutLaws @AsteOutLaws, qui potrai mandare un Asta oppure cercare un oggetto con un semplice Modulo!


# Handle all other messages with content_type 'text' (content_types defaults to ['text'])
@bot.message_handler(func=lambda message: True)
def echo_message(message):
    bot.reply_to(message, message.text)


bot.infinity_polling()
