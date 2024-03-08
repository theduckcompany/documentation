# Start/Enable the systemd service


Duckcloud lifecycle is managed by [Systemd service manager](https://systemd.io/) this bring several advantages:

- It allow to automatically start the service after a server boot/restart.
- It allow to sandbox the application and bring more security.
- It allow to provide in a safe way the secrets to the application.


### Start the service

First you can start you service by running:

!!! Run
    ```
    sudo systemctl start duckcloud.service
    ```

If you want to automatically start duckcloud at startup you can run this command:

!!! Run
    ```
    sudo systemctl enable duckcloud.service
    ```


### Check the service status


You can quickly check if everything by running:

!!! Run
    ```
    sudo systemctl status duckcloud.service
    ```


### Check the service logs

In case of error you can find details by running:

!!! Run
    ```
    sudo journalctl -xeu duckcloud.service
    ```
