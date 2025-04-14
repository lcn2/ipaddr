# ipaddr

print the host's IP addresses

We will attempt to determine IP address of this host.  By default we print the IP address of the default
route interface, unless `-i inter` is given in which case that specifically named interface is used.

If the default route interface cannot be determined (and if `-i inter` is not given),
then we will attempt to print all IP addresses for all interfaces.  However, the `-d` command option
will force a non-zero exit if the default route interface cannot be determined.

By default, only 1 IP address is printed.  However if IP addresses for all interfaces must be
processed (because default route interface cannot be determined), then multiple IP addresses
may be printed.  However the `-1` command option will force a non-zero exit if more than one
IP address would have been printed.

By default, we do not print localhost addresses, unless the -0 flag is given.

If a given interface has both an IPv4 and IPv6 address, only the IPv4 address is printed.

If `-4` is given, only IPv4 address are printed: no IPv6 address are printed.
If `-6` given, only IPv6 address are printed.


# To install

```sh
sudo make install
```


# Example(s)

```sh
$ /usr/local/bin/ipaddr
192.168.50.170
```

```sh
$ /usr/local/bin/ipaddr -6
fe80::cc81:bfe:face:c0a
```


# To use

```
/usr/local/bin/ipaddr [-h] [-v level] [-V] [-d] [-1] [-4] [-6] [-0] [-i inter] [-L]

    -h          print help message and exit
    -v level    set verbosity level (def level: 0)
    -V          print version string and exit

    -d          print only the default route interface IP address (def: try default route interface, then print all IP interfaces)
    -1          print only one IP address or nothing (def: try default route interface, then print all IP addresses)

    -0          print localhost IP addresses (def: do not print localhost IP addresses)

    -4          print only IPv4 addresses (def: print both IPv4 and IPv6 IP addresses)
    -6          print only IPv6 addresses (def: print both IPv4 and IPv6 IP addresses)

                NOTE: -4 and -6 conflict

    -i inter    use only the inter interface (def: try default interface, then use all interfaces)
    -L          list known interfaces names and exit

Exit codes:
     0      all OK
     1      no IP addresses could be determined
     2      -h and help string printed or -V and version string printed
     3      command line error
     4      default route interface addresses could not be determined and -d used
     5      multiple single IP address found and -1 used
     6      -l used and no interface names could be determined
 >= 10      internal error

ipaddr version: 1.1.0 2025-04-13
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/ipaddr/security/policy)".
