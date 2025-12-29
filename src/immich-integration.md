# Immich Integration

## Hide Immich search bar
> [!TIP]
> When Immer in Bewegung embeds photos in **image view** (see below), the search bar from Immich will be displayed unless you use small a css modification in your Immich settings.

Add
```
body:has(#search-chips:target) #asset-selection-app-bar,
body:has(#search-chips:target) #search-chips {
  display:none;
}
```
to **User Icon** > **Admininstration** > **Settings** > **Theme Settings**: Custom CSS.

![img](img/immich_search_bar.png)

## Usage of Immich API
To make use of Immich API you need to allow CORS, example snippet to add to **/etc/caddy/Caddyfile**

```
immich.your-server-name.duckdns.org {

        header {
                Access-Control-Allow-Origin  https://your-server-name.duckdns.org
                Access-Control-Allow-Methods "GET, POST, PUT, DELETE, OPTIONS"
                Access-Control-Allow-Headers "Content-Type, x-api-key"
        }

        @options method OPTIONS
        respond @options 204

        reverse_proxy http://localhost:2283

}
```
