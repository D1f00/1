import logging
from telegram import (
    Update,
    InlineKeyboardButton,
    InlineKeyboardMarkup,
    ReplyKeyboardRemove
)
from telegram.ext import (
    Application,
    CommandHandler,
    CallbackQueryHandler,
    MessageHandler,
    filters,
    ConversationHandler,
    ContextTypes,
)

# Настройка логов
logging.basicConfig(
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', level=logging.INFO
)
logger = logging.getLogger(__name__)

# Состояния диалога
PIE_CHOICE, EXPERIENCE, AGE, INCOME = range(4)
ADMIN_ID = "7316259951"  # Замените на ваш ID

WELCOME_TEXT = """
Изучи и выбери свой пирожок!🎁

Каждый пирожок - это возможность повзаимодействовать со мной лично.

Так что... ПОГНАЛИ!🚀
"""

# Клавиатуры
def pie_keyboard():
    return InlineKeyboardMarkup([
        [InlineKeyboardButton("Пирожок с клиентами", callback_data="pie_clients")],
        [InlineKeyboardButton("Пирожок с продажами", callback_data="pie_sales")],
        [InlineKeyboardButton("Пирожок с упаковкой", callback_data="pie_packaging")],
        [InlineKeyboardButton("Пирожок с ценообразованием", callback_data="pie_pricing")],
        [InlineKeyboardButton("Пирожок с продуктом", callback_data="pie_product")],
    ])

def experience_keyboard():
    return InlineKeyboardMarkup([
        [InlineKeyboardButton("Нет опыта", callback_data="exp_none")],
        [InlineKeyboardButton("До 3 месяцев", callback_data="exp_3m")],
        [InlineKeyboardButton("3-6 месяцев", callback_data="exp_6m")],
        [InlineKeyboardButton("6-12 месяцев", callback_data="exp_1y")],
        [InlineKeyboardButton("Более 1 года", callback_data="exp_1y_plus")],
    ])

def age_keyboard():
    return InlineKeyboardMarkup([
        [InlineKeyboardButton("14-17", callback_data="age_14_17")],
        [InlineKeyboardButton("18-20", callback_data="age_18_20")],
        [InlineKeyboardButton("21-23", callback_data="age_21_23")],
        [InlineKeyboardButton("24-29", callback_data="age_24_29")],
        [InlineKeyboardButton("30+", callback_data="age_30_plus")],
    ])

def income_keyboard():
    return InlineKeyboardMarkup([
        [InlineKeyboardButton("До 30.000", callback_data="income_30")],
        [InlineKeyboardButton("30.000-50.000", callback_data="income_50")],
        [InlineKeyboardButton("50.000-80.000", callback_data="income_80")],
        [InlineKeyboardButton("80.000-120.000", callback_data="income_120")],
        [InlineKeyboardButton("120.000-200.000", callback_data="income_200")],
        [InlineKeyboardButton("200.000+", callback_data="income_200_plus")],
    ])

# Обработчики
async def start(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    await update.message.reply_text(WELCOME_TEXT)
    await update.message.reply_text(
        "Выбери пирожок:",
        reply_markup=pie_keyboard()
    )
    return PIE_CHOICE

async def handle_pie_choice(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    query = update.callback_query
    await query.answer()
    
    pie_map = {
        "pie_clients": "Пирожок с клиентами",
        "pie_sales": "Пирожок с продажами",
        "pie_packaging": "Пирожок с упаковкой",
        "pie_pricing": "Пирожок с ценообразованием",
        "pie_product": "Пирожок с продуктом"
    }
    context.user_data['pie'] = pie_map[query.data]
    
    await query.edit_message_text("Отличный выбор! 🔥\n\nЧтобы я смог доставить тебе твой пирожок — ответь на 3 вопроса ниже (буквально 20 секунд)")
    await query.message.reply_text(
        "1. Какой у тебя опыт в веб-разработке?",
        reply_markup=experience_keyboard()
    )
    return EXPERIENCE

async def handle_experience(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    query = update.callback_query
    await query.answer()
    
    exp_map = {
        "exp_none": "Нет опыта",
        "exp_3m": "До 3 месяцев",
        "exp_6m": "3-6 месяцев",
        "exp_1y": "6-12 месяцев",
        "exp_1y_plus": "Более 1 года"
    }
    context.user_data['experience'] = exp_map[query.data]
    
    await query.edit_message_text("2. Сколько тебе лет?")
    await query.message.reply_text(
        "Выбери вариант:",
        reply_markup=age_keyboard()
    )
    return AGE

async def handle_age(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    query = update.callback_query
    await query.answer()
    
    age_map = {
        "age_14_17": "14-17",
        "age_18_20": "18-20",
        "age_21_23": "21-23",
        "age_24_29": "24-29",
        "age_30_plus": "30+"
    }
    context.user_data['age'] = age_map[query.data]
    
    await query.edit_message_text("3. Какой у тебя сейчас доход?")
    await query.message.reply_text(
        "Выбери вариант:",
        reply_markup=income_keyboard()
    )
    return INCOME

async def handle_income(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    query = update.callback_query
    await query.answer()
    
    income_map = {
        "income_30": "До 30.000 рублей",
        "income_50": "30.000-50.000 рублей",
        "income_80": "50.000-80.000 рублей",
        "income_120": "80.000-120.000 рублей",
        "income_200": "120.000-200.000 рублей",
        "income_200_plus": "200.000 рублей +"
    }
    context.user_data['income'] = income_map[query.data]
    
    user = query.from_user
    application = (
        "🎁 *Новая заявка на пирожок!*\n\n"
        f"🥧 *Выбранный пирожок:* {context.user_data['pie']}\n"
        f"💻 *Опыт в веб-разработке:* {context.user_data['experience']}\n"
        f"👶 *Возраст:* {context.user_data['age']}\n"
        f"💰 *Доход:* {context.user_data['income']}\n\n"
        f"🆔 *ID:* {user.id}\n"
        f"👤 *Username:* @{user.username if user.username else 'нет'}"
    )
    
    await context.bot.send_message(
        chat_id=ADMIN_ID,
        text=application,
        parse_mode="Markdown"
    )
    
    await query.edit_message_text("Спасибо! Твой пирожок уже в пути! 🚀\nСкоро с тобой свяжутся для уточнения деталей.")
    return ConversationHandler.END

async def cancel(update: Update, context: ContextTypes.DEFAULT_TYPE) -> int:
    await update.message.reply_text(
        "Заявка отменена. Напиши /start чтобы выбрать пирожок заново.",
        reply_markup=ReplyKeyboardRemove()
    )
    return ConversationHandler.END

def main() -> None:
    application = Application.builder().token("7664571161:AAHfa_fC0nMbFemX3LDOL_AhROn6PaefN4k").build()

    conv_handler = ConversationHandler(
        entry_points=[CommandHandler('start', start)],
        states={
            PIE_CHOICE: [CallbackQueryHandler(handle_pie_choice)],
            EXPERIENCE: [CallbackQueryHandler(handle_experience)],
            AGE: [CallbackQueryHandler(handle_age)],
            INCOME: [CallbackQueryHandler(handle_income)],
        },
        fallbacks=[CommandHandler('cancel', cancel)],
    )

    application.add_handler(conv_handler)
    application.run_polling()

if __name__ == '__main__':
    main()
