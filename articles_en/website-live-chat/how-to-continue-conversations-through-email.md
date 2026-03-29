# How to continue conversations through email?Your customers can continue their chat conversations with your agents through email threads. This may be required under

the following circumstances.

  - No agents are available, and the customer leaves a message in the chat.

  - The customer leaves the chat before the agent replies.

For this to work, the contact should have an email address in the Katalis.app CRM.

Obtaining email addresses of contacts​

You can prompt/update customer emails into Katalis.app through the following ways.

1.  From Katalis.app SDK​
    
    If customer email is known, you can supply it into Katalis.app via the setUser method in our SDK.

2.  From pre-chat form​
    
    If you enable a mandatory pre-chat form, the conversation starts with a screen as shown below:

3. From Email collect Prompt​

When the pre-chat form is disabled, and the customer's email is unknown, Katalis.app starts a conversation with an email
collect prompt.

Note: When Captain is enabled on an inbox, the email collect prompt is automatically suppressed. Captain will handle
conversations directly, even outside business hours. The email collect prompt will only be sent if Captain hands off the
conversation to a human agent or if Captain is not configured for the inbox.

Conversation Continuity​

Note: Enable conversation continuity in self-hosted installations with the help of this guide.

If the customer's email address is updated through any of the options mentioned above and they leave the chat while the
agent has replied, the following happens.

  - The customer receives an email thread with a conversation summary. They can reply to that email and continue the
    conversation.

  - The agent receives the customer replies from email in their Katalis.app dashboard, continued over the existing
    conversation thread.

The email icon in the chat bubble indicates that the customer has replied through email.Last updated on Dec 15, 2025