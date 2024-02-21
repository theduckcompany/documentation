# Using Apache 2.4 as Reverse Proxy

!!! tldr ""
    Should you experience problems with Apache, we recommend that you ask the Apache community for advice, as we cannot provide support for third-party software and services.

!!! example
    ```
    ProxyPass /api/v1/ws ws://duckcloud.fr:2342/api/v1/ws
    ProxyPassReverse /api/v1/ws ws://duckcloud.fr:2342/api/v1/ws
    ProxyPass / http://duckcloud:2342/
    ProxyPassReverse / http://duckcloud:2342/
    ProxyRequests off
    ```

The [official documentation](https://httpd.apache.org/docs/2.4/mod/mod_proxy_wstunnel.html) explains in detail, how to configure Apache Web Server 2.4 to reverse proxy WebSockets.

!!! example ""
    **Help improve these docs!** You can contribute by clicking :material-file-edit-outline: to send a pull request with your changes.
