# Wildcard URL support in website live-chat campaigns

The website live-chat campaigns support wild card URL patterns. While building a URL pattern, consider the following

behavior in mind.

In Katalis.app, every URL pattern should start with http:// or https://.

## Running the campaign on the exact URL​

If you add an exact URL like https://katalis.app/app, then the URLs with trailing slashes or the URL params or the hash
params would not match. Some examples for exact match definitions are as follows.

  - https://katalis.app/app would match https://katalis.app/app/ or ``https://katalis.app/app?test_param=1`

  - https://katalis.app/app?test_param=test_value would not
    match https://katalis.app/app or https://katalis.app/app#test_hash_param

## Running the campaign ignoring the URL parameters​

To ignore the URL params or hash params, you can add a trailing slash in the URL. For
eg: https://katalis.app/app/ would match all the following URLs.

  - https://katalis.app/app/

  - https://katalis.app/app

  - https://katalis.app/app/?test=1

  - https://katalis.app/app/#test

## Running the campaign in all sub-directories​

You can use the * character in the URL if you want to match all the sub-directories. For
eg: https://katalis.app/* would match to the following URLs

  - https://katalis.app/

  - https://katalis.app/app

  - https://katalis.app/app/subdirectory

## Running the campaign in all subdomains​

To match the current domain and subdomains, you can use the pattern {*.}? in the URL. For
eg: https://{*.}?katalis.app/ would match to the following URLs

  - https://katalis.app

  - https://app.katalis.app

  - https://www.katalis.app

_Last updated on Apr 10, 2024_
