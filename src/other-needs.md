# Other needs

## Expose web server to internet
Using Caddy this becomes easy. Deploy the server with

```text title="/etc/caddy/Caddyfile"
your-server-name.duckdns.org {

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
You can browse in folder queries/ to see the SQL queries used by the application. This can be useful if you want to make same analtycis as the application in some other software.
