# Updating robots.txt to Allow Katalis.app Assistant to Crawl Your Website

Katalis.app uses Firecrawl internally to fetch and index your website content. This allows the Katalis.app Assistant to answer

questions using your site’s information.

However, if your website’s robots.txt has Disallow rules, Firecrawl will respect them and skip crawling those pages.

When that happens:

  - No documents from your website will be added to Katalis.app

  - The Assistant will not receive any additional context

  - Answers may become incomplete or generic

To ensure the Assistant works properly, you need to allow Firecrawl to crawl your website.

## Step 1: Check Your robots.txt

Visit:

https://yourdomain.com/robots.txt

Look for any Disallow: entries that might block user agents.

## Step 2: Add an Allow Rule for Firecrawl

Ask your website admin or developer to add the following lines to the robots.txt file:

User-agent: FirecrawlAgent
Allow: /

This tells Firecrawl that it is permitted to crawl your entire site, even if other bots are restricted.

Step 3: Save and Publish

After updating robots.txt, ensure the file is deployed and publicly accessible.

You can verify by visiting:

https://yourdomain.com/robots.txt

and checking that the new rules appear.

_Last updated on Dec 08, 2025_
