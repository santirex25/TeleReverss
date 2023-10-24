# FX Signal Copier Telegram Bot 💻💸

This Telegram bot allows users to enter trades directly from Telegram and get a detailed look at the risk-to-reward ratio with profit, loss, and calculated lot size. You can change specific settings such as allowed symbols, risk factor, and more from your personalized Python script and environment variables.

The FX Signal Copier Telegram Bot makes use of the MetaAPI cloud forex trading API for MetaTrader 4 to create a connection to a user's MetaTrader account to gather information such as account balance, open positions, and permissions to enter and close trades. The API works for both live and demo accounts.

Official REST and WebSocket API documentation for MetaAPI: https://metaapi.cloud/docs/client/

This bot is deployed using Heroku.

<b>UPDATE: AS OF FEBRUARY 18, 2023, THIS REPOSITORY IS A PUBLIC ARCHIVE. THIS VERSION OF THE MT4 FX SIGNAL COPIER TELEGRAM IS NO LONGER MAINTAINED HERE AND NOW USES RENDER FOR DEPLOYMENT. IT HAS BEEN MOVED TO THE FOLLOWING REPOSITORY HERE: https://github.com/ogunjobiFX/MT4-Forex-Signal-Copier-Telegram-Bot</b>

# Demonstration 🎥

![ezgif-4-a2f4e1b1a1](https://user-images.githubusercontent.com/54332223/180027398-36ddf07b-0f22-4589-9e02-8bd4031dc27b.gif)

# Installation ⚒️

Prerequisites:
- Telegram Account 
- Python 3 (https://www.python.org/downloads/)
- Git (https://git-scm.com/downloads)
- MetaAPI Account (https://app.metaapi.cloud/sign-up)
- Heroku Account (https://signup.heroku.com/)
- Heroku CLI (https://devcenter.heroku.com/articles/heroku-cli#pre-requisites)

***YouTube Demonstration:*** https://www.youtube.com/watch?v=QTCco30M3BY&t=5s

**(For Window Users: It is recommended to use a Git Bash terminal for installation)**

**1. Create a Telegram Bot**

Start a conversation with @BotFather on Telegram and create a new bot with a unique name. Save the given API token.

**2. Create or open a folder on your local machine and create a Python Virtual Environment**
```bash
mkdir telegram_bot
cd telegram_bot
python3 -m venv fx_telegram_bot
```

**3. Activate virtual environment**
```bash
Linux/MacOS: source fx_telegram_bot/bin/activate
Windows: source fx_telegram_bot/Scripts/activate

# Windows users can enter ".\fx_telegram_bot\Scripts\activate" in terminal if Git Bash is not used
```

**4. Install pip packages in virtual environment (Optional)**
```bash
pip install metaapi_cloud_sdk prettytable python-telegram-bot
```

**5. Download FX Signal Copier Telegram Bot Code**

Navigate to the code button at top of this repository and download the FX Signal Copier Telegram Bot as a zip file. Upon downloading, extract the folder to a location and transfer all individual files to telegram_bot/fx_telegram_bot. The individual files must be placed in this folder or the Heroku deployment will be unsuccessful.

**6. Set Up Heroku App**

Navigate to Heroku web app and create a new application with a unique name. Upon creation, go to app settings and navigate to **Config Vars**. Add the following environment variables (case-sensitive) for key and value excluding quotes.

|Key  | Value |
| ------------- | ------------- |
| TOKEN | "INSERT TELEGRAM BOT API TOKEN HERE" |
| APP_URL | "https://[INSERT NAME OF APP HERE].herokuapp.com/" |
| TELEGRAM_USER | "INSERT TELEGRAM USERNAME HERE" |
| API_KEY | "INSERT META API TOKEN HERE" (https://app.metaapi.cloud/token) |
| ACCOUNT_ID | "INSERT META API ACCOUNT ID HERE" (https://app.metaapi.cloud/accounts) |
| RISK_FACTOR | "INSERT PERCENTAGE OF RISK PER TRADE HERE IN DECIMAL FORM, ex: 5% = 0.05" |

**6. Deploy Heroku App**

Return to terminal and log in to Heroku app to initialize repository and deploy.
```bash
heroku login
git init
heroku git:remote -a "INSERT NAME OF APP HERE"
git add .
git commit -m "first deployment"
git push heroku master
```

If at any point you decide to make a change to any of the environment variables, all you have to do is navigate to the Heroku web app and edit the value. After making the change and saving, the application will automatically deploy with the new changes.

**Congratulations!** 🥳 If you followed these steps correctly, you should now be able to open a conversation with your bot on Telegram and calculate trade risk-to-reward along with placing trades. For help on how to use the bot, send the /help command for bot instructions and example trades.

# Features 💡
- Copy trades directly from Signal providers or personal analysis 
- Interact with MetaAPI to retrieve MT4 account information (Balance, Equity, Open Positions, etc.)
- Place all 6 order type trades from Telegram bot (Market Buy/Sell, Limit Buy/Sell, Buy/Sell Stop)
- Calculate risk-to-reward using stop loss and take profit and display size in pips and profit/loss (USD)
- Place up to two take profits and use half position size for each to maintain the risk-to-reward ratio
- Future Features: Trade confirmation, multiple TPs, trailing stop loss

# License 📝
&copy; 2022 Tosin Ogunjobi. All rights reserved.

Licensed under the MIT license.
