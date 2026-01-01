# Migration guide

This repository was renamed from **rir-ip** to **country-ip-blocks**.

## Migration steps

1. If only consuming raw text files: just update the download URL, no code changes needed
2. Update repository URLs in your code from `ipverse/rir-ip` to `ipverse/country-ip-blocks`
3. If parsing JSON: handle field renames (see below)

## What's changing

### Repository name
- Old: `ipverse/rir-ip`
- New: `ipverse/country-ip-blocks`

### File structure

The file structure remains the same:
```
country/ad/aggregated.json
country/ad/ipv4-aggregated.txt
country/ad/ipv6-aggregated.txt
```

### JSON format

**Old:**
```json
{
  "country": "Andorra",
  "country-code": "AD",
  "delegation-status": [
    "allocated",
    "assigned"
  ],
  "mode": "aggregated",
  "subnets": {
    "ipv4": [
      "46.172.224.0/19",
      "85.94.160.0/19"
    ],
    "ipv6": [
      "2a01:fb00::/29"
    ]
  }
}
```

**New:**
```json
{
  "country": "Andorra",
  "countryCode": "AD",
  "delegationStatus": [
    "allocated",
    "assigned"
  ],
  "exportMode": "aggregated",
  "prefixes": {
    "ipv4": [
      "46.172.224.0/19",
      "85.94.160.0/19"
    ],
    "ipv6": [
      "2a01:fb00::/29"
    ]
  }
}
```

**Changes:**
- `country-code` renamed to `countryCode`
- `delegation-status` renamed to `delegationStatus`
- `mode` renamed to `exportMode`
- `subnets` renamed to `prefixes`

### Plaintext format

The plaintext file format remains the same:

ipv4-aggregated.txt:
```
# Country: Andorra (AD)
# Address family: IPv4
# Delegation status: Allocated || Assigned
# Export mode: Aggregated
#
46.172.224.0/19
85.94.160.0/19
```

ipv6-aggregated.txt:
```
# Country: Andorra (AD)
# Address family: IPv6
# Delegation status: Allocated || Assigned
# Export mode: Aggregated
#
2a01:fb00::/29
```

### URL changes

**Old:**
```
https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ad/aggregated.json
https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ad/ipv4-aggregated.txt
https://raw.githubusercontent.com/ipverse/rir-ip/master/country/ad/ipv6-aggregated.txt
```

**New:**
```
https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/aggregated.json
https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/ipv4-aggregated.txt
https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/ipv6-aggregated.txt
```