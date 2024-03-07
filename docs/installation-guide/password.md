# Register your password 


You can let [systemd](https://systemd.io/CREDENTIALS/) and [systemd-creds](https://www.freedesktop.org/software/systemd/man/latest/systemd-creds.html) 
handle your master password.

### Why ?

All the files handled by Duckcloud are encrypted with a master password provided by you. Without it Duckcloud can't function 
properly as it can't read your files. For security reasons the master password is only kept encrypted in memory. So if the 
server stops or your machine restarts the memory is lost and so is the ability to Duckcloud to read your files. That's why 
you needs to give your password after each restart.

This manual step can be very tedious as it make your service unoperable after each restart until an admin have put the password. That's why we
propose a secure way to do it automatically.


!!! danger "Security note"
    You should register your password only if you trust your machine and the people on it. Everyone one with root access can easily seen your password in clear.


### How ?


#### Stop the service

First you needs to stop the service:

!!! Run
    ```
    sudo systemctl stop duckcloud.service
    ```

#### Generate the credentials:

The credentials are handled by [systemd](https://systemd.io/CREDENTIALS/) and the [systemd-creds](https://www.freedesktop.org/software/systemd/man/latest/systemd-creds.html) command.
This tooling allows to keep your password encrypted by using the [Trusted Platform Module](https://en.wikipedia.org/wiki/Trusted_Platform_Module) if available. 

This command needs to be run with the root permissions:

!!! Run
    ```bash
    systemd-ask-password -n | systemd-creds encrypt --name=password - /etc/duckcloud/password.cred
    ```

#### Enable the credentials:

You need to indicate to systemd that it needs to load the credentials previously generated. For that you needs
to uncomment a line inside `/usr/lib/systemd/system/duckcloud.service`:

!!! Run
    ```bash
    ```


#### Restart the service

Finally you can to start again the service:

!!! Run
    ```
    sudo systemctl start duckcloud.service
    ```
