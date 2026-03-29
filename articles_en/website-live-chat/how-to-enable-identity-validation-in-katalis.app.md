# How to enable identity validation in Katalis.app?Identity validation helps ensure that the conversations between your customers and support agents are private. It also

helps with disallowing impersonation.

Identity validation can be enabled by generating an HMAC.

The key used to generate HMAC for each web widget differs and can be copied from Inboxes -> Settings -> Configuration ->
Identity Validation -> Copy the token shown there.

You can generate HMAC in different languages, as shown below.

Generate HMAC​

PHP​

<?php

$key = '<webwidget-hmac-token>';
$message = '<identifier>';

$identifier_hash = hash_hmac('sha256', $message, $key);
?>

Javascript (Node.js)​

const crypto = require('crypto');

const key = '<webwidget-hmac-token>';
const message = '<identifier>';

const hash = crypto.createHmac('sha256', key).update(message).digest('hex');

Ruby​

require 'openssl'
require 'base64'

key = '<webwidget-hmac-token>'
message = '<identifier>'

OpenSSL::HMAC.hexdigest('sha256', key, message)

Elixir​

key = '<webwidget-hmac-token>'
message = '<identifier>'

signature = :crypto.hmac(:sha256, key, message)

Base.encode16(signature, case: :lower)

Golang​

package main

import (
    "crypto/hmac"
    "crypto/sha256"
    "encoding/base64"
    "encoding/hex"
)

func main() {
  secret := []byte("<webwidget-hmac-token>")
  message := []byte("<identifier>")

  hash := hmac.New(sha256.New, secret)
  hash.Write(message)
  hex.EncodeToString(hash.Sum(nil))
}

Python​

import hashlib
import hmac
import base64

secret = bytes('<webwidget-hmac-token>', 'utf-8')
message = bytes('<identifier>', 'utf-8')

hash = hmac.new(secret, message, hashlib.sha256)
hash.hexdigest()Last updated on Apr 10, 2024