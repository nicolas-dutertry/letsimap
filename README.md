# Let's IMAP

Cron job to manage Courier IMAP certificate based on Let's Encrypt certificate.

If you deploy a [Let's Encrypt](https://letsencrypt.org/) certificate with [Certbot](https://certbot.eff.org/) to your web server and want to use it with Courier IMAP daemon, this script will automatically manage it for you.

Every time the Let's Encrypt certificate is renewed, Let's IMAP will recreate the corresponding file for Courier IMAP.

## Installation

### Courier IMAP configuration

In file /etc/courier/imapd-ssl set the following parameters:

    TLS_CERTFILE=/etc/letsencrypt/live/HOSTNAME/imapd.pem
    TLS_TRUSTCERTS=/etc/letsencrypt/live/HOSTNAME/fullchain.pem

where you must replace _HOSTNAME_ with the public host name of your server.

Don't forget to reload Courier IMAP configuration.

### Install script

Clone this git repository and run the install script as root:

    # git clone https://github.com/nicolas-dutertry/letsimap.git
    # cd letsimap
    # ./install

## Certificate generation

The install script generates the certificate for Courier IMAP in the file /etc/letsencrypt/live/_HOSTNAME_/imapd.pem.

Every time the Let's Encrypt certificate will be renewed, imapd.pem will be automatically regenerated.
