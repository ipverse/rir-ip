# ipverse-rir-ip

Drop-in replacement for the country-based IP subnet lists currently available at http://ipverse.net 
based on Internet number resource usage data published by the Regional Internet Registries (RIR). 
Probably shouldn't be used for geolocating since the RIR data is rather generic.

This repository is updated daily.

## How to use

To download the delegated IPv4 subnets for Switzerland, try:
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv4-aggregated.txt```

To download the delegated IPv6 subnets for Switzerland, try:
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv6-aggregated.txt```

The subnet lists (IPv4 + IPv6 combined) are available in JSON format as well:
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/aggregated.json```
