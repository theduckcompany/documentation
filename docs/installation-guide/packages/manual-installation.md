
!!! danger "Getting Support"
    For production server, manual installation should be a last resort. If your package manager is supported you should use it. It would allow you to have a more effective support.


## From source

With Go's `install`, you can install duckcloud via:

!!! example
    ```
    go install github.com/theduckcompany/duckcloud/cmd/duckcloud@latest
    ```


The binary will be installed inside `$GOBIN`. You need to append `$GOBIN` to you `$PATH` env variable.

!!! code "~/.bashrc"
    ```
    export PATH="$GOBIN:$PATH"
    ```

## From Binaries

The [release page](https://github.com/theduckcompany/duckcloud/releases) includes precompiled binaries for Linux, macOS and Windows for every release.
