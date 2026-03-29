# How to setup an SSL certificate for your Help Center's custom domain?Using your own domain, like docs.your-company.com, makes your help center feel more trustworthy and on-brand. Katalis.app

allows you to use your own custom domain and would help you to secure your site with SSL certificates so that it's safe
for your visitors.

This guide walks you through setting up a custom domain for your Help Center portal in Katalis.app.

Note: This guide is for Katalis.app Cloud users. If you're using the self-hosted version, you'll need to set up and manage
the SSL certificate on your own.

TLDR: Add your custom domain in Katalis.app portal settings, update your DNS with the CNAME Katalis.app provides, and we will
issue the SSL certificate. Once it's ready, your Help Center will be live and accessible to your customers.

Step 1: Set up your custom domain in portal settings

Log in to your Katalis.app dashboard and go to the Help Center you want to connect with your custom domain. Click
on Settings, then scroll to the Custom Domain section. Click the Add custom domain button to begin the setup.

You'll now see a prompt asking for your custom domain. Enter the domain where you want your Help Center to be available
(e.g., docs.yourdomain.com). This is the website address your customers will visit to access your documentation.

Next, you'll be shown the DNS settings you need to add so we can confirm that the domain is yours and connect it to your
Help Center. You’ll need to copy this information and update your DNS provider accordingly.

If you’re not sure how to do it, you can use the option on the screen to email these details to your developer.

Step 2: Update your DNS with the CNAME record

You must point your custom domain to Katalis.app by creating a CNAME record.

Host: docs
Type: CNAME
Value: Katalis.app.help

Instructions vary by DNS provider:

Using Cloudflare:

You can find the setting under the "DNS" tab.

Note: Make sure that the SSL encryption mode is set to Full in Cloudflare (You can view this under SSL/TLS -> Overview).

Using AWS Route 53:

You can find the setting under the "Route53" service.

If you're using a different DNS provider, the steps are generally the same. Look for the DNS settings section and add a
CNAME record as described. If you’re unsure how to do this, just search for instructions specific to your provider using
a phrase like How to add a CNAME record on [Your DNS Provider].

This step links your domain to Katalis.app’s servers. Once it’s done, we’ll have everything we need, your portal details
and the domain configuration to issue the SSL certificate and make your Help Center live.

Step 3: Getting an SSL certificate​

Katalis.app provides SSL certificates for all cloud customers on paid plans who set up a custom domain for their Help
Center portal.

This step happens automatically. Once you add the CNAME record to your DNS, our server will verify the domain and begin
issuing the SSL certificate. This usually takes just a few minutes, but in some cases, depending on your DNS provider
and how long they take to update records, it may take up to 24–48 hours.

You can track the status of your SSL certificate right from the Katalis.app dashboard. Initially, you’ll see the status as
Awaiting Verification. This means we’re still confirming your domain setup before the certificate is issued.

If there are any issues during the SSL verification process like an incorrect CNAME record or DNS propagation delays,
you’ll see an error message next to the status on your dashboard. Hover over the status indicator to view more details
about what went wrong and what you need to fix. This helps you quickly identify and resolve any problems in the setup
process.

Once the verification is successful and the SSL certificate is issued, the status will change to 'Live' on your
dashboard. This means your Help Center is now securely available at your custom domain. Your customers can visit the URL
and browse the content.Last updated on Aug 07, 2025