# ScalaHosting Review: Key Findings & Performance Test Notes

This repository accompanies the GoogieHost review of ScalaHosting. It provides the supporting context for the review's hands-on testing, including uptime monitoring, response-time checks, and load testing.

## Review at a glance

The review looks at ScalaHosting's hosting plans, usability, performance, uptime, customer support, security, backups, data-center locations, and pricing. The overall takeaway is that ScalaHosting is worth considering for users who value managed VPS options, responsive support, security tools, and reliable uptime. Buyers should also compare renewal pricing and understand the performance and backup limitations before choosing a plan.

## Key takeaways

- **Uptime observations:** The review reports 100% uptime during a monitored period of 4,052 hours and 32 minutes. Its longer uptime report lists monthly averages of 99.98%–99.99% for January–March 2026 and yearly averages of 99.98%–99.99% for 2023–2025.
- **Load-test result:** The review reports 5,537 requests with no failed requests in its k6 test and an average response time of 5.695 ms. It also notes that no exact test scenario was configured, so this result should not be treated as a universal capacity benchmark.
- **Response time by location:** The review's Bitcatcha observations indicate that response times were higher in locations farther from the selected server. Choosing a data center close to the intended audience can matter.
- **Customer support:** The review describes quick responses during its support checks, particularly through live chat and phone support. It notes that billing and pre-sales availability is not 24/7.
- **SPanel control panel:** ScalaHosting's in-house SPanel is presented as an alternative to cPanel, with website, email, DNS, and security management features.
- **Security features:** The review highlights free Let's Encrypt SSL, 2FA, CSF Firewall, ModSecurity, SSH access, and SShield security monitoring.
- **Backups:** The review says automatic offsite backups are provided every 24 hours. One limitation is that restoring an offsite backup requires restoring the entire server rather than a single website.
- **Pricing:** Introductory prices can be attractive, but renewal costs are higher. The review's pricing section lists WordPress plans starting at $5.36/month; displayed prices may change.
- **Best fit:** The review positions ScalaHosting as an option for individuals and businesses looking for VPS-focused hosting, management tools, security, and support.

## Strengths

- Managed and self-managed VPS options.
- SPanel control panel as an alternative to paid cPanel licensing.
- Strong uptime observations during the review's monitoring period.
- Helpful support experience during the review's checks.
- Security tools such as SShield, ModSecurity, SSL, and 2FA.
- Daily offsite backups and a range of data-center locations.

## Points to consider

- Renewal pricing can be considerably higher than introductory pricing.
- Response time depends partly on the visitor's distance from the selected data center.
- Offsite backup restoration is described as a full-server restore, not a single-site restore.
- The review notes that SSD coverage is more limited outside VPS hosting.
- The k6 test did not define an exact scenario, so its result should not be interpreted as a guaranteed performance level for every workload.

## Performance testing context

The review describes a sample managed VPS plan using the Sofia, Bulgaria data center for its hands-on tests. It discusses GTmetrix, uptime monitoring, k6 load testing, and Bitcatcha response-time checks. Test outcomes depend on the plan, application, configuration, test location, and measurement period.

The repository includes these supporting files:

| Path | Purpose |
|---|---|
| `k6/load-test.js` | k6 load-test script |
| `scripts/ttfb-check.sh` | Measures DNS, connection, TLS, and TTFB timings using curl |
| `scripts/uptime-check.sh` | Checks HTTP status and response time |
| `data/uptime-log.csv` | Uptime observations |
| `data/ttfb-by-location.csv` | TTFB observations by test location |
| `data/k6-results.csv` | k6 run summaries |

**Note:** The figures summarized above are findings stated in the GoogieHost review. The scripts and CSV files are supporting test resources; not every figure in the article is necessarily reproduced in the current CSV files.

## Full review

For the complete methodology, screenshots, plan details, and full analysis, read the [ScalaHosting Review on GoogieHost](https://googiehost.com/blog/scalahosting-review/).


## Additional Related Resources

- [Watch the ScalaHosting review on YouTube Shorts](https://youtube.com/shorts/8SpplUtWHjI?si=vs8Ihz9hGUqAf3eg)
- [Watch the ScalaHosting review on DTube](https://d.tube/watch/QjqvWrq2AsXogt9F4e1dXX)

## Google Search Console verification reference

The following verification meta tag was supplied for reference:

```html
<meta name="google-site-verification" content="QM7rYTErGm7vRxH_7vT29N6QedWlkoaPPINmd5onx-s" />
```

**Important:** Adding this tag to this README does not verify a website in Google Search Console. For verification, the tag must be placed in the `<head>` section of the homepage HTML for the website being verified.
