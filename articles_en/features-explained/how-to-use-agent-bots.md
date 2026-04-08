# How to use Agent bots?

AgentBot can seamlessly integrate with your Katalis.app inbox as a customer query handling bot. With Katalis.app, you can

easily connect your custom bot logic to conversation handling via AgentBot's API.

By connecting AgentBot to your inbox, all new conversations will automatically be assigned a 'bot' status. Katalis.app will
send conversation events to your bot URL as webhook events, allowing AgentBot to respond through the Katalis.app API in
real-time.

## How does the AgentBot work?

Explained below in a typical workflow of an AgentBot.

1.  The AgentBot receives events such as widget_triggered, message_created, and message_updated based on customer
    interactions.

2.  The AgentBot processes the received information to generate an appropriate response.

3.  The AgentBot can also utilize external system APIs to gather additional customer information, such as order status
    or booking triggers.

4.  The AgentBot can utilize services such as Rasa, Dialogflow, or Lex for intent detection.

5.  The AgentBot can post the generated response back into the widget by utilizing Katalis.app APIs such as message_create.

6.  The AgentBot can toggle a conversation status to open to hand off the conversation to a human agent.

7.  It continues to monitor open conversations to provide contextual information to the support agent.

## How does the Human-Agent handoff work?

When an agent bot is connected to an inbox, conversations are created with a "pending" status, allowing it to triage the
conversation before passing it on to a human agent. If the bot determines that a human agent's assistance is needed, it
can use the conversation update API to change the status to "open."

Sometimes the agents would want to push back a conversation which was handed off, back again into the bot queue. Agents
can return a handed-off conversation to the bot queue by changing the status back to "pending”.

## How can I use the AgentBot?

Listed below are a few examples.

1.  Businesses with high volume customer support queries can utilize an AgentBot to authenticate and filter queries,
    reducing the workload on human agents and improving the efficiency of customer support.

2.  E-commerce websites can integrate the AgentBot with their existing databases, providing customers with real-time
    updates on order and shipping status, as well as answering other related queries.

3.  News and content websites can use the AgentBot to send recommendations to users via card messages.

4.  Hotel and movie booking websites can use the AgentBot to handle bookings, reservations and answering related
    queries, providing customers with a seamless and convenient booking experience.

Examples

1.  Hotel booking implementation using Dialogflow.

2.  Example implementation using Rasa.

Also, look into interesting ways to leverage bot-message types on Katalis.app.

## Creating agent bots

## How to create agent bots in your Katalis.app account?

You can create agent bots from the account settings. Go to Settings -> Bots. You will see an option like the one below.

Click on "Add Bot" to create a new bot. You will see an option to provide a name, avatar and a webhook URL.

## How to connect an inbox to a bot?

Open the inbox where you want to link the bot. In Bot Configuration, pick the bot that should manage the conversations.
After you click Save, you’ll start getting webhook events each time a new conversation or message is created.

For more details about the events that are supported in the webhooks, please visit the Webhook documentation here.

_Last updated on May 02, 2025_
