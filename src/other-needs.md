# Other needs

## Expose web server to internet
Using Caddy this becomes easy. Deploy the server with

```text title="/etc/caddy/Caddyfile"
immich.your-server-name.dedyn.io {

        # Generate password storing hash with: caddy hash-password
        basic_auth {
                # Username "iib", password "bewegung"
                iib $2a$14$basROD3Y0cLE.VqXd.h89.akCQDKzhp6IH9ND2CRFyEICkMrKn3AO        
        }

        root /var/www/iib/

}
```

### Alternatives
* Add support for https
    * E.g. via Let's encrypt
* Use user authentication via
    * Authelia, or
    * Authentik, or
    * Client certificates, or
    * Port forwarding over SSH (e.g. using Termius on Android)
    
## List over SQL Queries
You can browse the folder `queries/` if you want to see what SQL queries the app is using. This can be useful if you want to make some analytics in another other software.
