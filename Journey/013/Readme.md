# Configure auto-renew w Cerbot - part 1

## Introduction

LetsEncrypt only issues certs for 90 days.  In order to not have to manually request renewal, you can configure a cron job to check at any frequency you like to determine if your cert is getting close to renewal and it will run the commands to send a renewal request. 

## Use Case

- This is useful if you plan to use the cert for greater than 90 days to have it auto renew.

## Cloud Research

- Ran into issue in testing (Errors below) that it requires an authentication script.  I am looking into how to configure this. 

 PluginError('An authentication script must be provided with --manual-auth-hook when using the manual plugin non-interactively.

## Social Proof

✍️ Show that you shared your process on Twitter or LinkedIn

[Tweet](https://twitter.com/disneyplus/status/1333426467988901888/photo/1)
