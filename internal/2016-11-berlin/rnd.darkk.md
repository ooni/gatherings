Random stuff
============

*Green* website may be False Negative — e.g. if the website has 99% failure rate and that's a stub from the proxy.

Possible data sources of Internet blackouts:
- BGP data (where? how to understand it?)
- [NDT traffic measurements data](https://www.measurementlab.net/tools/ndt/)
- [Google traffic](https://www.google.com/transparencyreport/traffic/) transparency reports
- [Tor metrics](https://metrics.torproject.org/userstats-relay-country.html)
- [Steam stats](http://store.steampowered.com/stats/)
- Cloudflare data (where?)
- Twitter & Instagram approx amount of geotagged posts (TBD: estimate via API)

Possible data sources of interesting stuff going on:
- downforeveryoneorjustme.com — imaginary partnership to get logs and understand country-specific requests
- Certificate transparency logs

DNS middlebox detection & fingerprinting methods:
- response to EDNS query
- response to oversized query
- response to two-queries-one-packet
- more inspiration from https://tools.ietf.org/html/rfc5966 and https://tools.ietf.org/html/rfc7766

Create "canonical" ooniprobe Dockerfile, build & publish to docker hub.

Verify that ooniprobe uses compression 1) to fetch data 2) to POST raw reports.

ooniprobe should ignore invalid SSL cert (continue connection), and store all the data regarding every received cert. Should this data be uploaded to certificate transparency reports?

We should not attempt to reduce fingerprintability of ooniprobe infinitely. It's OK to be fingerprinted:
- by an ISP having to grep **all** the netflow logs retroactively to identify ooniprobe using websites test-list to fingerprint it
- by an ISP IDS triggered by various protocol manipulation tests

Website failing both from probe an control may deserve online verification from other vantage points to rule out control server hitting same CAPTCHA as ooniprobe.

Known-fail cases may not need a control measurement or may have huge (hours) TTL for control data.

We can't put a link to User-Agent of control server (like good crawler), but we can set up DNS PTR & disclaimer page at :80 and :443.

Interesting pipeline output:
- something better than a screenshot of raw data to include to country-specific report
- what websites are tested but are *not* included in the citizenlab test lists

Data extraction-transformation:
1. Separating *anomalous* from *normal* measurements, group by categories (anomaly categories or website categories?)
2. Anomalous measurements: a) types of anomalies: DNS, TCP/IP, HTTP-diff, HTTP-fail; b) amount of anomalies & successes
3. Testing period - "density" of reports and measurements across the time for various slices for each color-code: Country, Endpoint, (Country+Endpoint)
4. Automate detection of blockpages – separate Cloudflare captcha (yellow) from state blockpage (red)

There are gaps in timestamps of the full list of measurements (that is running for an ~hour). What can explain such gaps? Is it cumulative effect of timeouts caused by well-known dead websites? Does shuffle (simulated) solve the issue?
