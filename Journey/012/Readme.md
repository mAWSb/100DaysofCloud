# Fixed my issue with LetsEncrypt cert

## Cloud Research

- My error ultimaltey was human error, when I initially setup the certiifcate via certbot, I used www. in front of the domain name.  This was causing a certificate mismatch errror and not allowing for the the cert to be validated.  I removed the cert and created a new one with the correct domain name and it worked as it should.  Sometimes causing the issue (in test) is the best way to learn.

## Social Proof

✍️ Show that you shared your process on Twitter or LinkedIn

[Tweet](https://twitter.com/realmawsb/status/1332438255074160640)