# How to create and use custom attributes?

Katalis.app allows you to track additional information about your conversations and contacts beyond the standard data

attributes like name, email, and location. These additional pieces of information are called custom attributes and can
be anything you want to track. Listed below are a few examples of custom attributes.

  - Subscription plan

  - Subscribed date

  - Signup date

  - Most ordered item

  - Ordered product link

  - Last transaction date

Custom data attributes allow you to attach additional information to a conversation or customer, such as purchase
history or account status. This information can be used to better understand and segment your customer base.

The only difference between custom and standard attributes is standard data attributes automatically get updated.

## How to create a custom attribute?

Step 1. Go to Settings → Custom Attributes. Click on the “Add Custom Attribute” button.

Step 2. A modal will open up, asking details about the new custom attribute. Fill these details in. Here is an example:

These are the inputs required to create the custom attribute:

1.  Applies to
    
    Attribute type (Conversation/Contact).

2.  Display name
    
    Act as a label while rendering custom attribute.

3.  Key
    
    Unique identifier attached to the custom attribute.

4.  Description
    
    Description of the custom attribute.

5.  Type
    
    Text, Number, Link, Date, List, and Checkbox.

Note: You cannot create a custom attribute with the same key twice in the account.

Step 3. Once you enter the details, click the ”Create” button. If the request is successful, a message "Custom attribute
added successfully" will be displayed.

## How to use a conversation custom attribute?

You can add conversation custom attributes to a conversation from the conversation sidebar. Follow the steps described
below.

Step 1. On your dashboard, when you open a particular conversation, you’ll find a section that reads “Conversation
Information”. Click on the + sign to expand it.

Step 2. You’ll see an option that reads “Add Attributes” followed by a dropdown of all the Custom Attributes on your
account. Use the search bar to narrow down on the name of the attribute you’re looking for. Or click on one to select
it. If you need to create a new one instead, use the “Create new attribute” button from the same dropdown.

Step 3. Based on the type of attribute you added (list, checkbox, text, etc.), populate it at your will. Here are a
couple of examples:

To edit/delete/copy an attribute, hover on it to see the options.

## How to use a contact custom attribute?

There two ways to set custom attributes for contacts.

## Set attributes via SDK method

To set a contact custom attribute, call setCustomAttributes method as follows.

window.$Katalis.app.setCustomAttributes({
  key: value,
  // Key is a unique identifier which is already defined while creating a custom attribute
  // Value should be based on type (Currently support Number, Date, String and Number)
  // Double-check that your keys always have a JSON-valid value
  // You need to flatten nested JSON structure while using this function
});

Example:

window.$Katalis.app.setCustomAttributes({
  key: value,
  // Key is a unique identifier which is already defined while creating a custom attribute
  // Value should be based on type (Currently support Number, Date, String and Number)
  // Double-check that your keys always have a JSON-valid value
  // You need to flatten nested JSON structure while using this function
});

You can view these attributes in the contact/conversation sidepanel.

To delete a custom attribute, use deleteCustomAttribute as follows.

window.$Katalis.app.deleteCustomAttribute("attribute-key");

Example:

window.$Katalis.app.deleteCustomAttribute("signUpDate");

Note: Prior to version v1.22, all the attributes rendered as text. Please create new definition to display the value
properly.

## Set attributes via contact side panel

For adding Contact Attributes, follow the same procedure as described above for conversation custom attributes, but use
the Contact Attributes section of your chat sidebar instead. This is what it would look like:

Based on the type of attribute you added (list, checkbox, text, etc.), populate it at your will. Here is an example:

_Last updated on Apr 10, 2024_
