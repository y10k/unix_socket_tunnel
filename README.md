unix_socket_tunnel
==================

unix domain socket tunnel utility.

Requirements
------------
Ruby is required because this utility is ruby script.

Description
-----------

This script tunnels unix domain socket to another path.
It is supposed to tunnel a socket of ssh-agent.

1. Default is quiet. It displays the log on the screen with the `-v`
   or `-l` option.
2. It monitors the parent process and exits when the parent process is
   finished. It is supposed to start in the background from login
   shell. It is able to change the process ID to be monitored with the
   `-w` option.
3. The default umask(2) is `0077`, and the tunnel destination socket
   refuses access from group and other. It is able to change umask
   with the `-u` option.
4. It checks the security of the tunnel destination directory. It is
   able to change security check level with
   `--dir-access-deny-mode-mask` option.

Usage
-----

```sh
$ unix_socket_tunnel -h
Usage: unix_socket_tunnel [options] CONNECT_PATH LISTEN_PATH
    -v, --verbose
    -l, --log-level=LEVEL
    -w, --watch-pid=PID
        --accept-timeout=SECONDS
        --io-chunk-size=BYTES
    -u, --umask=OCTETS
        --dir-access-deny-mode-mask=OCTETS
```

