# Using Caddy 1 as Reverse Proxy

!!! tldr ""
    Should you experience problems with Caddy, we recommend that you ask the Caddy community for advice, as we cannot provide support for third-party software and services.

For Duckcloud to work properly, you need to enable websockets and transparent proxying:

!!! example
    ```
    example.com {
        proxy / duckcloud:2342 {
            websocket
            transparent
        }
    }
    ```

Please refer to the [official documentation](https://caddyserver.com/v1/docs/websocket)
for further details.

!!! example ""
    **Help improve these docs!** You can contribute by clicking :material-file-edit-outline: to send a pull request with your changes.
