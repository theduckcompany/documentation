# Using HAPROXY as Reverse Proxy

!!! tldr ""
    Should you experience problems with Haproxy, we recommend that you ask the Haproxy community for advice, as we cannot provide support for third-party software and services.

```bigquery
defaults
    #Defaults used in frontend and backends
    #Defined here to avoid repitition
    #Can be overwritten in frontends and/or backends
    log global
    option logasap
    mode http
    timeout connect 30000ms
    timeout client 30000ms
    timeout server 30000ms
    timeout tunnel 120000ms
    timeout queue 5000ms

##########################################################

#Frontend config
frontend fe-duckcloud
    #'photo' is the name of the subdomain
    #TLS certs should be referenced here, maybe created by dehydrated, certbot, ...
    bind *:443 ssl crt /etc/ssl/localcerts/wildcard.example.com.pem

    #SNI-Detection
    #Can be removed, if not needed
    acl sni_photo hdr(host) -i photo.example.com
    #Use Backend if domain (acl is set) detected
    use_backend be-duckcloud if sni_photo

    #Every unflagged request goes here, may target to another backend as well
    default_backend be-duckcloud

##########################################################

#Backend config
#be-duckcloud is the name of the backend referenced in frontend
backend be-duckcloud
    retries 3
    option forwardfor
    no option httpclose
    
    #Local Duckcloud-Instance
    server photo 127.0.0.1:2342
```

!!! example ""
    **Help improve these docs!** You can contribute by clicking :material-file-edit-outline: to send a pull request with your changes.
