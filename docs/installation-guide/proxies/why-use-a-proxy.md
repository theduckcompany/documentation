# Why use a Proxy? #

If you install Duckcloud on a public server outside your home network, **always run it behind a secure
HTTPS reverse proxy**. Your files and passwords will otherwise be transmitted in clear text and can be intercepted
by anyone, including your provider, hackers, and governments. Backup tools and file sync apps may refuse to
connect as well.

If you don't already have a one setup we advice you to try [Caddy 2](./caddy-2.md). This proxy is the easiest to setup and 
handle [automatically create](https://caddyserver.com/docs/caddyfile/directives/tls) 
and update [Let's Encrypt](https://letsencrypt.org/) HTTPS certificates.

!!! example ""
    **Help improve these docs!** You can contribute by clicking :material-file-edit-outline: to send a pull request with your changes.
