# V6Gen tool
This small script gives you the possibility to generate an IPv6 address randomly or based on the FQDN.

## Generation with the FQDN
The algorithm is pretty basic. The script take the hostname part of the FQDN and convert it in hexadecimal. If the hostname is too long, it remove vowels. If a this point he can't generate an IPv6 address, it the start removing characters per characters until a valid IPv6 is generated.

## Installation
Via pip:
```
pip install v6gen
```

## Usage
```
➜ v6gen --help
usage: v6gen [-h] (-r | -n NAME) [-R] range

positional arguments:
  range                 IPv6 network range

optional arguments:
  -h, --help            show this help message and exit
  -r, --random          Generate random machine ipv6
  -n NAME, --name NAME  Generate IPv6 based on the machine name
  -R, --reverse         Get reverse IP for ARPA zone
```

Get an IP address based on the FQDN:
```
➜ v6gen 2001:db8:beef:cafe::/64 -n myserver.blah.net
2001:db8:beef:cafe:6d79:7365:7276:6572/128
```

## ToDo
 * Add random IP generation
 * Add reverse IP part
 * Add an option for keeping last numbers in the hostname (eg: `34` in `my-service34`)

## License
This script is released under MIT License.