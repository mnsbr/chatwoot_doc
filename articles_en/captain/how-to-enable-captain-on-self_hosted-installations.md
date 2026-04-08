# How to enable Captain on self-hosted installations?

Captain is an AI assistant that helps you respond faster and more accurately. With Bring Your Own Key (BYOK), you can

use your own API key from OpenAI or any compatible AI service. You control the data, costs, and which model is used. In
a self-hosted setup, Captain only sends data to the AI model you choose.

This guide will show you how to enable Captain in your self-hosted Enterprise Edition, add your API key, and set up a
custom model if you want.

## Prerequisites

Before you begin, make sure that you have:

  - Katalis.app Enterprise Edition with a paid plan.

  - Admin access to the Super Admin Console.

  - A valid OpenAI API key.

  - (Optional) A self-hosted OpenAI-compatible API endpoint.

  - (Optional) A Firecrawl API key for a better documentation crawling.

## Enabling Captain in the Super Admin Console

To enable Captain at the installation level:

Log in to the Super Admin Console. Navigate to Settings → Captain.

Fill in the configuration fields:

1.  OpenAI API Key (Required) – The key for authenticating requests to OpenAI or a compatible service.

2.  OpenAI Model (Required) – Default is gpt-4o-mini. You may choose another supported model like gpt-5.

3.  OpenAI API Endpoint (Optional) – Enter your custom API endpoint if you are using a self-hosted model.

4.  Firecrawl API Key (Optional) – Recommended for better website and documentation crawling.
    
    Click Submit to save your configuration.

## Enabling Captain for an Account

After enabling Captain globally, activate it for individual accounts:

1.  In the Super Admin Console, go to Accounts.

2.  Select the account you want to enable Captain for and click Edit.

3.  Under the Premium Features section, toggle Captain on.

4.  Save the changes.

## Troubleshooting

If Captain is not responding as expected:

  - Verify that the OpenAI API key is correct and active.

  - Check that the model name matches a supported model.

  - Ensure your Firecrawl API key is valid if using crawling.

  - Confirm that Captain is enabled both at the installation and account levels.

If Captain is still not responding, review the Katalis.app server logs for both the web and worker processes to identify
any errors, and share those error details with the support team for further assistance.

_Last updated on Aug 15, 2025_
