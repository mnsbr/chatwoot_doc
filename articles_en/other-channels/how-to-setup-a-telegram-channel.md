# How to setup a Telegram channel?Step 1. Go to Settings → Inboxes → “Add Inbox”.

Step 2. Click on the "Telegram" icon.

Step 3. Create a new telegram bot using Telegram BotFather.

Step 4. Enter the API token of the Telegram bot and click on "Create Telegram Channel".

Step 5. "Add agents" to your Telegram inbox.

The inbox setup is complete.

Step 6. Go to the Inbox settings page and verify that the inbox name matches the bot username created using BotFather.

Step 7. Send a message to the Telegram bot. Check Katalis Telegram inbox for the new message.

FAQs

Does Katalis support Telegram Business Bot accounts?

Yes — support for Telegram Business-mode bots was added in Katalis v4.3.0 (18 Jun 2025).

How to enable Business Bots?

1.  In @BotFather run /business_mode, choose your bot, and confirm.

2.  Create a new Telegram inbox in Katalis (Settings → Inboxes → Add Inbox → Telegram) and paste the same bot token.

3.  Katalis auto-detects Business Mode and registers the correct webhook.

4.  For best results, keep this Business bot in its own inbox, separate from any standard bot you already use. ￼

Known issues with Business Bot

• 24-hour reply window – Telegram only lets the bot (and Katalis) reply within 24 hours of the customer’s last message.
￼

• If a user has previously chatted with the same bot outside Business Mode, replies may appear to come from the bot
rather than the Business account; creating a dedicated Business bot & inbox avoids this confusion.

• The Telegram Business API is currently less feature-rich than the regular Bot API (e.g., no typing indicators, limited
message types). Keep expectations accordingly.Last updated on Jun 19, 2025