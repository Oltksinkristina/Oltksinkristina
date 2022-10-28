- #Христя [28.10.2022 19:50]
import audioop
from email.mime import audio
from importlib.resources import open_text
import logging
from telegram import Update, ChatAction
from telegram.ext import CallbackContext, CommandHandler, Updater, MessageHandler, Filters
import uuid

logging.basicConfig(
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    level=logging.INFO
)

state = 1
life = 5

updater = Updater(token="5485896186:AAGVQdnXFJ-p_4gW02mmrQNsmRQ_95nkid8", use_context=True)
dispatcher = updater.dispatcher

def start_command_handler(update: Update, context: CallbackContext):
    global state
    if state == 1:
        context.bot.send_message(chat_id=update.effective_chat.id,  text=f"Привіт, {update.effective_chat.first_name}!") 
        text = 'вітаю в грі "Вгадай що за пісня". Памятайте в вас всього 5 житів. Ну що ж розпочнемо'
        context.bot.send_message(chat_id=update.effective_chat.id, text=text)
        with open('280t⃨o⃨g⃨u⃨_s⃨h⃨i⃨n⃨k⃨i⃨21_S⃨T⃨R⃨A⃨N⃨G⃨E⃨_M⃨I⃨S⃨T⃨E⃨R⃨I⃨O⃨.mp3.mp3', 'rb') as file:
            context.bot.send_chat_action(update.effective_chat.id, ChatAction.UPLOAD_AUDIO)
            context.bot.send_audio(update.effective_chat.id, audio=file)
        text_1 = '''
1: Edzi - Frozen
2: loved_you_first_anglijskaja_muzika_-_one_direction_(z2.fm).mp3
3: 280t⃨o⃨g⃨u⃨_s⃨h⃨i⃨n⃨k⃨i⃨21_S⃨T⃨R⃨A⃨N⃨G⃨E⃨_M⃨I⃨S⃨T⃨E⃨R⃨I⃨O⃨.mp3.mp3
'''
        context.bot.send_message(chat_id=update.effective_chat.id, text=text_1)
        state += 1
    else:
        pass

def text_message_handler(update: Update, context: CallbackContext):
    message = update.message.text
    global state
    global life
    if state == 2 and life > 0:
        if message == '3':
            text = '''
1: Panic-At the Disco - Houses of Memories.m4a
2: kiss_me_anglijskaja_muzika_-_ed_sheeran_(z2.fm).mp3
3: aaron_switch_dancin.mp3.mp3      
'''
            context.bot.send_message(chat_id=update.effective_chat.id, text="Вітаю правильний вибір. Вгадай що за пісня")
            with open('aaron_switch_dancin.mp3.mp3', 'rb') as file:
                context.bot.send_chat_action(update.effective_chat.id, ChatAction.UPLOAD_AUDIO)
                context.bot.send_audio(update.effective_chat.id, audio=file)
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            state += 1
        elif message == '1' or message == '2':
            text = "Неправильно. Подумайте ще"
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            life -= 1
    elif state == 3 and life > 0:
        if message == '2':
            text = '''
1: Speedy_Songs_-_On_my_own_(mp3.xmuz.pro)-1.mp3
2: black_widow_anglijskaja_muzika_-_iggy_azalea_feat_rita_ora_(z2.fm).mp3
3: eminem_mockingbird_(mp3bit.cc).mp3.mp3
'''
            context.bot.send_message(chat_id=update.effective_chat.id, text="Вітаю правильний вибір. Вгадай що за пісня")
            with open('eminem_mockingbird_(mp3bit.cc).mp3.mp3', 'rb') as file:
                context.bot.send_chat_action(update.effective_chat.id, ChatAction.UPLOAD_AUDIO)
                context.bot.send_audio(update.effective_chat.id, audio=file)
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            state += 1
        elif message == '1' or message == '3':
            text = "Неправильно. Подумайте ще"
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            life -= 1
    elif state == 4 and life > 0:
        if message == '2':
            text = '''
1: Meghan Trainor - My Kind Of Present.mp3
2: The Rare Occasios - Notion.mp3
3: Mr_Kitty_After_Dark_Slowed_Down_dYZgs_Ds2QQ_140.mp3.mp3
'''
            context.bot.send_message(chat_id=update.effective_chat.id, text="Вітаю правильний вибір. Вгадай що за пісня")
            with open('Mr_Kitty_After_Dark_Slowed_Down_dYZgs_Ds2QQ_140.mp3.mp3.', 'rb') as file:
                context.bot.send_chat_action(update.effective_chat.id, ChatAction.UPLOAD_AUDIO)
                context.bot.send_audio(update.effective_chat.id, audio=file)
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            state += 1

#Христя [28.10.2022 19:50]
        elif message == '1' or message == '3':
            text = "Неправильно. Подумайте ще"
        context.bot.send_message(chat_id=update.effective_chat.id, text=text)
        life -= 1
    elif state == 5 and life > 0:
        if message == '1':
            text = '''
1: Julian Era & Matt Wolff - By My Side.mp3
2: CNCO feat. Meghan Trainor & Sean Paul - Hey DJ.mp3
3: Playboi_Carti_Sky.mp3.mp3
'''
            context.bot.send_message(chat_id=update.effective_chat.id, text="Вітаю правильний вибір. Вгадай що за пісня")
            with open('Playboi_Carti_Sky.mp3.mp3', 'rb') as file:
                context.bot.send_chat_action(update.effective_chat.id, ChatAction.UPLOAD_AUDIO)
                context.bot.send_audio(update.effective_chat.id, audio=file)
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            state += 1
    elif message == '2' or message == '3':
            text = "Неправильно. Подумайте ще"
            context.bot.send_message(chat_id=update.effective_chat.id, text=text)
            life -= 1
  
   
  
start_handler = CommandHandler('start', start_command_handler)
dispatcher.add_handler(start_handler)

echo_handler = MessageHandler(Filters.text & ~Filters.command, text_message_handler)
dispatcher.add_handler(echo_handler)

# Start bot
updater.start_polling()
