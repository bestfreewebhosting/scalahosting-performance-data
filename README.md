# ScalaHosting Performance Data

Open data and test scripts from long-term use of ScalaHosting: uptime tracking, TTFB by location and a k6 load test.

The full write-up with screenshots and analysis is in the [ScalaHosting review on GoogieHost](https://googiehost.com/blog/scalahosting-review/). This repository holds the raw material so anyone can check the numbers or re-run the tests on their own server.

> **Disclosure:** this repository is maintained by the team behind GoogieHost, which earns a commission on some ScalaHosting links. Run the scripts yourself and compare with other sources.

## What's inside

| Path | What it is |
|---|---|
| `k6/load-test.js` | k6 load test with thresholds for failures and P95 response time |
| `scripts/ttfb-check.sh` | Measures DNS, connect, TLS and TTFB for a URL with curl |
| `scripts/uptime-check.sh` | Logs HTTP status and response time to a CSV (run it from cron) |
| `data/uptime-log.csv` | Uptime log (timestamp, status, response time) |
| `data/ttfb-by-location.csv` | TTFB measurements by test location |
| `data/k6-results.csv` | Summary of each k6 run |

## Test setup

Fill this in so others can reproduce the results.

- **Plan tested:** `[plan name, e.g. managed cloud VPS size]`
- **Control panel:** `[SPanel / cPanel]`
- **Data center:** `[location]`
- **Stack:** `[WordPress version, PHP version, caching, CDN]`
- **Monitoring period:** `[start date] to [end date]`
- **Number of sites:** `[n]`

## Results summary

Copy the final numbers from the CSV files. Do not round in your favor.

| Metric | Result |
|---|---|
| Uptime over the monitoring period | `[x]%` |
| Median TTFB | `[x] ms` |
| k6 requests / failures | `[n] / [n]` |
| k6 P95 response time | `[x] ms` |

## How to run the tests

### 1. TTFB check

```bash
./scripts/ttfb-check.sh https://example.com
```

Run it from several locations (a VPS in each region or a monitoring service) and append the results to `data/ttfb-by-location.csv`.

### 2. Uptime log

```bash
# every 5 minutes
*/5 * * * * /path/to/scripts/uptime-check.sh https://example.com >> /path/to/data/uptime-log.csv
```

### 3. Load test with k6

Install k6, then:

```bash
TARGET_URL=https://example.com k6 run k6/load-test.js
```

Only test sites you own or have permission to test.

## Method notes and limits

- Results depend on the plan, data center, site configuration and caching. A different plan can behave very differently.
- Load tests from one location measure that route, not the whole world.
- Uptime checks every few minutes can miss short outages.

## License

Scripts: MIT (see `LICENSE`). Data: CC BY 4.0, so you can reuse it with attribution.

## Contributing

Ran the same tests on your own ScalaHosting account? Open an issue or a pull request with your CSV and test setup.
