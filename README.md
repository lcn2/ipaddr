# ipaddr

Print the IP address for the primary route.


# To install

```sh
sudo make install
```


# Example

```sh
$ /usr/local/bin/ipaddr
192.168.50.170
```


# To use

```
/usr/local/bin/ipaddr [-h] [-v level] [-V]

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

Exit codes:
     0      all OK
     2      -h and help string printed or -V and version string printed
     3      command line error
     4      neither ipconfig nor ifconfig found
 >= 10      internal error

ipaddr version: 1.0.1 2025-04-11
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/ipaddr/security/policy)".
