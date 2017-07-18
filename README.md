# letsimapd

Cron job to manage Courier IMAP certificate based on Lets Encrypt certificate.

If you deploy a [Let's Encrypt](https://letsencrypt.org/) certificate with [Certbot](https://certbot.eff.org/) to your web server and want to use it with Courier IMAP daemon, this script will automatically manage it for you.

Every time the Let's Encrypt certificate is renewed, letsimapd will recreate the corresponding file for Courier IMAP.
