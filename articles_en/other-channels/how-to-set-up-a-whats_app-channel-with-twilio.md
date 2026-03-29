# How to Set Up a WhatsApp Channel with Twilio?Manage your WhatsApp business account conversations through Katalis.app. You have two provider options:

1.  WhatsApp Cloud API (preferred way)

2.  Twilio

This guide will walk you through the setup process.

Prerequisites

1.  A valid phone number

2.  A Twilio account. If you don't have one, create it here: https://www.twilio.com/en-us/messaging/channels/whatsapp

Using Twilio API

There are two ways to use Twilio with Katalis.app:

1.  Regular way without messaging service

2.  With messaging service

Setting Up Twilio Without Messaging Service

Log into your Twilio account and click on "Create New Account"

Complete all required fields and finish the account creation process

Copy your Account SID, Auth Token, and phone number. If you haven't added a phone number to your Twilio account yet, do
so before proceeding.

Log into your Katalis.app account, click on Settings > Inbox > Add Inbox and select Whatsapp

Enter your Account SID, Auth Token, and WhatsApp number here

Add agents to manage your WhatsApp inbox

Go to Settings > Inbox, select your inbox, click on Configuration, and copy your webhook URL

Return to your Twilio dashboard

1.  Go to Twilio Console → Phone Numbers → Manage → Active Numbers

2.  Click on your WhatsApp number.

3.  Click Configure

4.  Under Messaging, check the field “Webhook (When a message comes in)”.

5.  Update the webhook URL.

That's it! You're all set to start sending WhatsApp messages through Katalis.app.

Setting Up Twilio with a Messaging Service

Setting up Twilio with a messaging service requires additional steps compared to the regular setup.

Navigate to Messaging > Services and click "Create Messaging Service" button.

Fill in all the required fields in the subsequent steps till you reach here. Copy your messaging service ID and click
“Save”.

Log into your Katalis.app account. When creating an inbox, check the "Use Twilio Message Service" box. Then copy and paste
your Account ID, Message Service ID, and Token into the appropriate fields.

Go to your Twilio dashboard, navigate to Messaging > Services > Select Service > Integration, and paste your Webhook URL
here.

That's it—you're all set! You can now start sending WhatsApp messages through Katalis.app.

FAQ’s

What types of WhatsApp templates does Katalis.app support when using Twilio?

Currently, Katalis.app does not support templates with Twilio.

I'm using Twilio Studio. Are there additional steps needed to make it work?

If you use Twilio Studio for a custom conversation flow, updating the webhook URL directly will break your existing
integration.

Follow these steps instead:

1.  Identify the step in your flow where you want the “agent handoff” to happen.

2.  Add a “make http request widget” as shown below with the given values.

3.  Ensure your flow can handle user responses to agent replies.Last updated on Feb 25, 2026