# country-ip-blocks (formerly rir-ip)

> **📢 Heads up:** This repo has a new name and the data format has changed. Check out [MIGRATION.md](MIGRATION.md) for what you need to update.

## 🔍 Try it online

Look up any IP address or prefix at **[Lens by ipverse](https://lens.ipverse.net)** to see its country and AS information.

## Overview

Ready-to-use IPv4 and IPv6 prefixes by country (ISO 3166-1 alpha-2), sourced from all five regional internet registries (RIR). Aggregated and updated daily.

## 📍 Need more accurate geolocation?

This dataset shows where IP ranges are officially *delegated* - useful for administrative and regulatory purposes. For more accurate operational geolocation based on actual network assignments, check out **[geo-ip-blocks](https://github.com/ipverse/geo-ip-blocks)**.

| Dataset | Best for |
|---------|----------|
| [country-ip-blocks](https://github.com/ipverse/country-ip-blocks) | Administrative/regulatory use cases |
| [geo-ip-blocks](https://github.com/ipverse/geo-ip-blocks) | Operational geolocation |

## Formats

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

## How to use

Download prefixes for a specific country (Andorra in these examples):

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

### Bulk download

Download all countries in a single archive from the [latest release](https://github.com/ipverse/country-ip-blocks/releases/latest):
```bash
curl -LO https://github.com/ipverse/country-ip-blocks/releases/latest/download/country-ip-blocks.tar.gz
tar -xzf country-ip-blocks.tar.gz
```

### Want more granular control?

Instead of blocking an entire geographic region, it might be more effective to block specific internet providers based on their autonomous system number (ASN). Check out [as-ip-blocks](https://github.com/ipverse/as-ip-blocks) for more information.

## Use cases
- Block countries at the firewall (for compliance or security reasons)
- Geo-based access control and traffic routing
- Network research and statistical analysis
- Threat hunting and security research

## Recent changes

- **2026-01-17**: Added bulk download archive in [releases](https://github.com/ipverse/country-ip-blocks/releases/latest)
- **2026-01-03**: Repo renamed from `rir-ip` to `country-ip-blocks` and JSON format updated to use camelCase. Check [MIGRATION.md](MIGRATION.md) if you're already using this data.
- 2025-05-04: Removed country code EU (non-standard code that RIPE only kept for historical reasons)

## Questions or issues?

Head over to the [feedback repo](https://github.com/ipverse/feedback) if you have questions, issues, or suggestions.

## License

This data is released under [CC0 1.0 Universal](LICENSE).
