# Let's IMAP

Cron job to manage Courier IMAP certificate based on Let's Encrypt certificate.

If you deploy a [Let's Encrypt](https://letsencrypt.org/) certificate with [Certbot](https://certbot.eff.org/) to your web server and want to use it with Courier IMAP daemon, this script will automatically manage it for you.

Every time the Let's Encrypt certificate is renewed, letsimap will recreate the corresponding file for Courier IMAP.

## Installation

### Courier IMAP configuration

In file /etc/courier/imapd-ssl set the following parameters:

TLS_CERTFILE=/etc/letsencrypt/live/_HOSTNAME_/imapd.pem

TLS_TRUSTCERTS=/etc/letsencrypt/live/_HOSTNAME_/fullchain.pem

where _HOSTNAME_ is the public hostname name of your server.

### Script files

Clone this git repository and run the install script as root.
