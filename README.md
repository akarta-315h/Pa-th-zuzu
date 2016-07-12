# Pa(th)zuzu! (v1.6.1)
Checks for PATH substitution vulnerabilities, logs the commands executed by the vulnerable executables and injects a reverse shell with the permissions of the owner of the process.

#How to make it work
- `curl https://raw.githubusercontent.com/ShotokanZH/Pa-th-zuzu/master/pathzuzu.sh > pathzuzu.sh`
- `chmod +x pathzuzu.sh`
- `./pathzuzu.sh`
```
 __      /___    \ ___    ___
|__) /\ (  | |__| ) _//  \ _//  \|
|   /--\ \ | |  |/ /__\__//__\__/. v1.6.1

Usage: /usr/local/bin/pathzuzu [-e command] [-r address:port] [-t seconds] /path/to/command [args]
        -e command      Execute command if target is vulnerable
        -r address:port Starts reverse shell to address:port
        -t seconds      Timeout. Kills target after $seconds seconds

Extra flags, requiring -e or -r:
        -g gid  Run command/r.shell only if the group is $gid
        -u uid  Run command/r.shell only if the user is $uid

Note: SUID files can bypass the -t flag, it's not a kill-proof solution.
Process may hang because of that.
```

Returns 0 if the executable is vulnerable, 1 otherwise.

Logs are saved in `pathzuzu.sh.log` ( `$(basename "$0").log` )

Demostration (warning: in asciinema on some [very tiny] devices the right part of the screen it's not viewable even while in landscape):

[![Pa(th)zuzu](http://i.imgur.com/dtXuSQX.gif)](https://asciinema.org/a/9u6g8nd2mb6p31v2g7co9ee1l?autoplay=true)
