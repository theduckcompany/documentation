# Service configuration

!!! tldr ""
    You can configure most of the service behaviours via the environment variables. If your service is 
    started via systemd thoses are loaded from `/etc/duckcloud/var_lib`. Note that changes to the config 
    options listed below always require a restart to take effect. 



| Environment                | Cli flag           | Default              | Description                                                |
|----------------------------|--------------------|----------------------|------------------------------------------------------------|
| DUCKCLOUD_FOLDER           | --folder           | /usr/share/duckcloud | Specify you data directory location.                       |
| DUCKCLOUD_HTTP_PORT        | --http-port        | 5764                 | Web server port number.                                    |
| DUCKCLOUD_HTTP_HOST        | --http-host        | 0.0.0.0              | Web server IP address.                                     |
| DUCKCLOUD_LOG_LEVEL        | --log-level        | info                 | Log message verbosity LEVEL. (debug, info, warning, error) |
| DUCKCLOUD_SELF_SIGNED_CERT | --self-signed-cert | false                | Generate and use a self-signed HTTPS/TLS certificate.      |
| DUCKCLOUD_TLS_CERT         | --tls-cert         | -                    | Public HTTPS certificate file (.crt)                       |
| DUCKCLOUD_TLS_KEY          | --tls-key          | -                    | Private HTTPS key file (.key)                              |
