# WhatsApp Message Bomber / Crash Tool
Python script for crashing whatsapp


This tool is intended for educational purposes only – to demonstrate how automated message sending works and to raise awareness about spam and abuse risks. Do not use it to harass, annoy or harm others. Misuse may violate WhatsApp’s Terms of Service and local laws. Use responsibly and only with explicit permission from the target.

# Features
Interactive Console UI – colorful prompts, logo display and input validation.

Country Code & Number Entry – builds the full international phone number.

Configurable Crash Count – user sets how many messages to send (max 15 per session).

WhatsApp Web Automation – uses Selenium to open WhatsApp Web, compose a message, and repeatedly click the send button.

Auto‑Driver Management – webdriver_manager fetches the correct ChromeDriver version automatically.

Error Handling – catches invalid inputs, connection issues and element loading failures.

Number Confirmation – asks if you want to change the number before starting.

# How It Works
The script clears the screen and displays a logo.

You enter:

Country code (without +, e.g., 254 for Kenya)

Victim’s phone number (without country code)

Number of “crashes” (message sends, max 15)

You confirm the full phone number.

The script launches a Chrome browser (using Selenium) and opens:

text
https://web.whatsapp.com/send?phone=<full_number>&text=Hello
It waits for WhatsApp Web to load and for the message input box to appear.

It then clicks the send button repeatedly (as many times as you specified), with a 2‑second delay between sends.

After finishing (or if an error occurs), the browser closes.

Note: You must already be logged into WhatsApp Web in Chrome (the bot does not handle QR scanning – so scan the QR code manually the first time you run it).

# Prerequisites
Python 3.7+

Google Chrome (latest version)

Internet connection

# Installation
Clone or download this repository.

Install the required Python packages:

bash
pip install selenium colorama webdriver-manager
No manual ChromeDriver setup is needed – webdriver-manager handles it automatically.

# Usage
Run the script from your terminal / command prompt:

bash
python crash.py
Follow the on‑screen prompts:

Enter country code (e.g., 1 for USA/Canada, 91 for India, 44 for UK)

Enter the phone number (digits only, without leading zero or country code)

Enter number of crashes (1–15)

Confirm the final number (Y to change, N to continue)

The script will then open Chrome, load WhatsApp Web (you may need to scan the QR code if not already logged in), and send the message repeatedly.

⚠️ Important Notes
Maximum 15 crashes – hardcoded in the script to respect rate limits (the script warns you).

WhatsApp Web must be logged in – the script does not automate the QR login. Log in manually the first time and stay logged in.

The script uses a 2‑second delay between sends to avoid being blocked instantly.

If the send button’s XPath changes (WhatsApp updates its UI), the script may fail – you would need to update the XPath in the code.

# License
This project is provided “as is” for educational purposes only. MIT License. By using this tool, you agree to take full responsibility for your actions.
