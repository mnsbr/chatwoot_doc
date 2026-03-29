# How to setup a WhatsApp channel (Manual flow)?You can manage your WhatsApp business account conversations from Katalis.app. To set it up, you have two options to choose

your provider:

1.  WhatsApp Cloud API

2.  Twilio

We'll explain all the procedures in this guide.

Prerequisites

1.  You need a Meta Developer Account to setup WhatsApp API. If you dont have a developer account already click here to
    create one before proceeding

2.  A valid phone number

Using Whatsapp Cloud API

WhatsApp Cloud API is available to all businesses and individual developers. Since it's hosted on Meta's cloud
infrastructure, you no longer need to use third-party providers like Twilio, Zendesk, 360Dialog, or MessageBird
(Business Solution Providers) to host your WhatsApp Business API.

Set up your Business Profile

Create a professional WhatsApp business profile with your company name, description, and contact information. A
well-crafted profile helps customers recognise and trust your brand when they interact with you.

Log into https://business.facebook.com and click the create portfolio button in the dropdown menu under Home

Complete all required fields to set up your business portfolio.

Once you have created your business portfolio, it's time to create your Facebook app.

Setup your Facebook App

Log into https://developers.facebook.com/ and click the Create App button.

Complete the required fields

Click "Other" from the options

Choose "Business" as your app type

Enter your contact email address and choose your business portfolio from the dropdown menu.

Add Whatsapp to your app

After creating your app, you'll be directed to the app dashboard. From there, click "Add Product" and choose WhatsApp
from the available products list.

Click the "Set up" button for WhatsApp

Note: Before proceeding, verify your business with Meta. You'll need to submit documentation for verification, which is
required for full API access.

Set Up a Permanent WhatsApp Cloud API Access Token

You'll need to create a System User and generate a permanent token to maintain secure, uninterrupted access.

Log in to your Facebook developer account, select your WhatsApp app, and navigate to the Business settings page.

Click on "System Users" and add a new system user with the role Admin

Click the "Add Assets" button, select your app name, choose the "Full Control" option, and click "Assign assets."

Return to the system users page, select your newly created system user from the list, and click the "Generate new token"
button.

Select your app from the dropdown menu

Select these three permission levels for your token:

  - whatsapp_business_manage_events

  - whatsapp_business_management

  - whatsapp_business_messaging

Copy and save your token

Set Up WhatsApp Cloud API

To create a new Meta business account, select "create a business account" from the dropdown menu. If you already have a
business account, you can select it from the existing options. I'm selecting "create a business account". Click the
continue button.

Paste your permanent token here

Add your production ready phone number

Note: Meta requires a verified phone number for WhatsApp API setup. You can verify your number using an OTP (one-time
password).

Once you have added and verified your phone number, the next step is configuring a webhook to receive inbound messages.

Connecting Your Katalis.app Account

Let's connect your Katalis.app account with your WhatsApp Cloud API

Copy your WhatsApp Phone Number ID and Business Account ID from this section

Log into your Katalis.app account, go to Settings > Inbox, and select WhatsApp channel

Enter your phone number, phone number ID, and business ID from your WhatsApp API setup

Add team members to your WhatsApp inbox

Copy the webhook URL and webhook verification token provided here

Set Up Your Webhook

We need to set up the WhatsApp webhook to receive incoming customer messages sent to your business number.

Your callback URL should be in the format of https://app.katalis.app/webhooks/whatsapp/{phone_number}.

Log into your Facebook developer account and navigate to WhatsApp > Configuration

Paste your Katalis.app webhook URL and verification token here, then click "Verify and Save"

Set up webhook permissions by subscribing to messages

That's it—you're all done! You can now start sending WhatsApp messages through Katalis.app.

FAQ’s

How to configure multiple numbers under a single Facebook app?

Facebook App allows configuring only a single Webhook endpoint. So create Inboxes in Katalis.app for all the numbers as
required. You will need to configure the Webhook URL provided for only one of these inboxes in the Facebook app for all
the other inboxes to work.

What type of Whatsapp templates are supported by Katalis.app ?

Please check the doc for more details about templates.

What are the supported media types?Last updated on Sep 15, 2025