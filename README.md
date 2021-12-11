# ipverse-rir-ip

Drop-in replacement for the IP subnet lists previously available at [ipverse.net](http://ipverse.net)
based on Internet number resource usage data published by the Regional Internet Registries (RIR). The data
is organized by country code (ISO 3166).

This repository is updated daily.

## How to use

To download the delegated IPv4 subnets for Switzerland, try:  
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv4-aggregated.txt```

To download the delegated IPv6 subnets for Switzerland, try:  
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv6-aggregated.txt```

The data (IPv4 + IPv6 combined) is available in JSON format as well:  
```$ curl https://raw.githubusercontent.com/ipverse/rir-ip/master/country/tl/aggregated.json```

The resulting JSON will look similar to this:  
```
{
  "country": "Timor-Leste",
  "country-code": "TL",
  "delegation-status": [
    "allocated",
    "assigned"
  ],
  "mode": "aggregated",
  "subnets": {
    "ipv4": [
      "43.254.56.0/22",
      "45.115.72.0/22",
      "59.153.132.0/22",
      "103.26.95.0/24",
      "103.30.112.0/22",
      "103.55.48.0/22",
      "103.99.26.0/24",
      "103.99.164.0/22",
      "103.112.36.0/22",
      "103.143.164.0/23",
      "103.148.184.0/23",
      "103.175.148.0/24",
      "103.176.12.0/23",
      "103.176.215.0/24",
      "103.198.176.0/22",
      "103.208.36.0/22",
      "103.238.116.0/22",
      "150.242.108.0/22",
      "180.189.160.0/20"
    ],
    "ipv6": [
      "2001:df0:840::/48",
      "2001:df0:7a00::/48",
      "2001:df0:f980::/48",
      "2001:df7:f980::/48",
      "2401:4b80::/32",
      "2402:d080::/32",
      "2405:1f00::/32",
      "2405:d540::/32",
      "2407:f2c0::/32"
    ]
  }
}
```

## Migrating from ipverse.net?

While all download-URLs pointing to [ipverse.net](http://ipverse.net) are being redirected to the corresponding file in this Github repository, you may chose to directly dowload the data from the new location. Here's how to change the download-URL:  

Old URL:  
```http://ipverse.net/ipblocks/data/countries/ch.zone```
```http://ipverse.net/ipblocks/data/countries/ch-ipv6.zone```

New URL:  
```https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv4-aggregated.txt"
```https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ch/ipv6-aggregated.txt"
