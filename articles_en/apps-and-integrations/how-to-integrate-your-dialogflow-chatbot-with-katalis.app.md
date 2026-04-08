# How to bring your Dialogflow chatbot to Katalis.app?

Chatbots are valuable for many customer engagement teams. They efficiently handle trivial questions and free human

agents to focus on more pressing issues.

Dialogflow and Rasa.ai are leading NLP (Natural Language Processing) platforms for building customized chatbots. In this
guide, we explain how you can create a bot in Dialogflow and easily integrate it with Katalis.app in seconds.

## How to create a Dialogflow bot?

Step 1. Go to your Dialogflow Console. We will be using Dialogflow Essentials for this article. Click on "Create Agent".
You will see options like these:

Step 2. You will need to create intents based on how you want your bot to respond. There will be 2 default intents in
the project called "Default Fallback Intent" and "Default Welcome Intent", as shown below.

This completes the basic bot configuration. Let us create a service account and connect it with Katalis.app.

You can also create additional intents for your specific use cases.
Katalis.app also supports advanced intents that enables agent handoff, interactive messages, etc.
refer: Scroll down to "Advanced Intents".

Step 3. Create a service account​. To connect this bot with Katalis.app, you need to create a service account on your
Google Cloud console. Navigate to the project console in Google cloud by clicking on the Project ID in the project
settings.

Navigate to IAM & Admin -> Service Accounts. You will see a view like the one shown below. Click on "Create Service
Account".

Provide a Service Account name and description as shown below.

To provide access, select Dialogflow API Client from the dropdown.

Continue and click on "Done". Now, you would be able to see the service listed in the dashboard. The next step is to
create a key so that it can be shared with Katalis.app. Click on the service account and click on the "Keys" tab. Then,
click on "Add Key". You will be able to see a screen like the one below.

Click on "JSON" and click on "Create". It will generate a key for your service account. Download the key and save it for
use later.

## Setting up Dialogflow Integration in Katalis.app​

Katalis.app has a native Dialogflow integration. You can connect your bot with Katalis.app in two quick steps.

Step 1. Go to "Settings -> Applications -> Dialogflow". Click on "Configure".

Step 2. Click the "Add a new hook" button. it will open up a setup modal. You need to add "Project ID," "Project Key
file," and an inbox to create a hook. Copy the contents of the key file downloaded earlier and paste it into the text
area.

That's it! The integration is complete. Test out the website inbox to see if the bot handles the initial query.

## Advanced Intents​

## Creating a handoff intent​

Once the user requests to talk to the agent, Dialogflow must inform Katalis.app that an agent can take over the
conversation.

Create an intent named "Handoff Intent" with training phrases like "Talk to an agent" or "Speak with an agent," etc. To
handle the handoff intent, we will create a "Custom Payload" response, as shown below.

{
  "action": "handoff"
}

Upon triggering an intent with the above payload, Katalis.app will toggle the status of the conversation to open and hand
it off to an agent.

## Interactive Messages​

Note: Interactive messages are supported only in the website inbox currently.

Katalis.app-Dialogflow integration also supports interactive messages. The following types of interactive messages are
supported.

1.  Options (follow-up supported)

2.  Cards

3.  Articles

## Creating an interactive message Intent​

You can create other interactive messages by changing the payload as mentioned in the interactive messages guide.

Create an intent with required training phrases and a "Custom Payload" response, as shown below for an options message.

## example for an options interactive message
{
  "content_type": "input_select",
  "content": "Select your favorite food from below",
  "content_attributes": {
    "items": [
      {
        "value": "I like sushi",
        "title": "Sushi"
      },
      {
        "title": "Biryani",
        "value": "I like biryani"
      },
      {
        "title": "Pizza",
        "value": "I like pizza"
      }
    ]
  },
  "private": false
}

When a user interacts with input messages and selects a value, it returns to Dialogflow. This allows for configuring
follow-up intents, such as creating an intent with the training phrase "I like biryani" for cases where the contact
selects the "biryani" option.

How can an agent transfer the conversation back to Dialogflow bot?​

When the Dialogflow bot is connected to an inbox, conversations are created with pending status instead of open. This
lets the initial triaging happen via the bot before the conversation is passed on to an agent. When handoff happens, the
conversation status is changed to open and the bot stops responding to it.

Sometimes the agents would want to push back a conversation that was handed off, back again into the bot queue. They can
do this by changing the conversation status back to pending. This will make the bot start responding to that
conversation again.

_Last updated on May 15, 2023_
