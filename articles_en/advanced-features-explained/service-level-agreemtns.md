# Service Level AgreementsAs the service provider, your Service Level Agreements (SLAs) are contractual arrangements between you and your

customers that define the level of service you commit to deliver. Your SLAs specify the expected performance metrics,
such as response times, availability, and resolution times, that you have agreed to provide. These SLAs hold you, as the
service provider, accountable for the quality of service you deliver, ensuring a consistent and reliable level of
support for your customers.

Katalis.app allows you to track the following metrics:

  - FRT (First Response Time): This metric refers to the time it takes for the agent to respond to a customer's initial
    inquiry or request. It is a critical measure of responsiveness, as customers expect prompt attention to their issues
    or questions.

  - NRT (Next Response Time): This metric focuses on the time between the customer's follow-up message and the agent's
    subsequent response. It ensures that the provider maintains a consistent level of engagement and keeps the
    conversation moving forward.

  - RT (Resolution Time): This metric captures the total time it takes for the agent to fully resolve the customer's
    issue or query, from the initial contact to the final resolution. It is a key indicator of the provider's efficiency
    and effectiveness in addressing customer needs.

Creating an SLA

You can configure SLAs from the settings page, an admin is allowed to create and delete SLAs, please note that you
cannot modify or change an SLA once it's created. To create an SLA, you need to add at-least one metric to be tracked.

Applying an SLA

You can use an automation rule to assign an SLA when a conversation event is triggered. Here's an example of assigning
the "Enterprise P0" SLA when a conversation is created by a specific email address and the priority is set to Urgent.

Once a conversation matches the SLA conditions and the events, the SLA policy is automatically applied. Once an SLA is
applied, it cannot be removed from the conversation.

Conversations with an active SLA, which is close to a threshold will show up in the UI as followsLast updated on Apr 15, 2024