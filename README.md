# country-ip-blocks (formerly rir-ip)

> **📢 Heads up:** This repo has a new name and the data format has changed. Check out [MIGRATION.md](MIGRATION.md) for what you need to update.

Ready-to-use IPv4 and IPv6 prefixes delegated to countries (ISO 3166-1 alpha-2), sourced from all five regional internet registries (RIR).

This dataset saves you from parsing RIR delegation files yourself - the prefixes are aggregated and ready to drop into firewalls, access control lists, or geo-routing configurations.
Updated daily when the underlying RIR data changes, so you always have current allocations.

> **Note:** This data shows which country an IP range is *delegated to* by the RIRs. It can be used for country-level blocking and compliance, but has limitations - delegated IPs can be used in other countries or routed globally. For pinpoint geolocation (city-level, actual user location), you'll need a dedicated geolocation service.

Available formats: JSON and plaintext

**JSON format**:
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

**Plaintext format** (Andorra IPv4):
```
46.172.224.0/19
85.94.160.0/19
```

**Plaintext format** (Andorra IPv6):
```
2a01:fb00::/29
```

## Recent changes

- **2026-01-03**: Repo renamed from `rir-ip` to `country-ip-blocks` and JSON format updated to use camelCase. Check [MIGRATION.md](MIGRATION.md) if you're already using this data.
- 2025-05-04: Removed country code EU (non-standard code that RIPE only kept for historical reasons)

## How to use

Download the delegated networks for a specific country (Andorra in these examples):


**Andorra in JSON format:**
```bash
curl https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/aggregated.json
```

**Andorra IPv4 addresses:**
```bash
curl https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/ipv4-aggregated.txt
```

**Andorra IPv6 addresses:**
```bash
curl https://raw.githubusercontent.com/ipverse/country-ip-blocks/master/country/ad/ipv6-aggregated.txt
```

### Want more granular control?

Instead of blocking an entire geographic region, it might be more effective to block specific internet providers based 
on their autonomous system number (ASN). Check out [as-ip-blocks](https://github.com/ipverse/as-ip-blocks) for more information.

## Use cases
- Block entire countries at the firewall (for compliance or security reasons)
- Geo-based access control and traffic routing
- Network research and statistical analysis
- Threat hunting and security research
- Figure out which IPs are delegated to specific countries
- Pretty much anything where you need to map country codes to their delegated networks

## Questions or issues?

Head over to the [feedback repo](https://github.com/ipverse/feedback) if you have questions, issues, or suggestions.

## License

This data is released under [CC0 1.0 Universal](LICENSE).
