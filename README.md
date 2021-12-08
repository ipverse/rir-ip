# ipverse-rir-ip

Drop-in replacement for the country-based IP subnet lists currently available at http://ipverse.net. Probabyly shouldn't used for geo-locating since the RIR data is too generic.

This repository is updated daily.

## How to use

To download the delegated IPv4 subnets for Switzerland, try:
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv4-aggregated.txt```

The files are available in JSON format as well, just replace the extension with .json.

