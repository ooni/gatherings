Rumbles of OONI Explorer user stories discussion
================================================

Who are main Explorer users from our standpoint? These are people needing evidence of censorship:
- Journalist — to write a story
- Lawyer — to prove a point
- Browser vendor — to display better error page instead of *Secure Connection Failed / The connection to the server was reset while the page was loading.*

Clusterisation of interesting data is useful. *"Facebook may be broken"* is
more valuable than *https://fbcdn.com/a/b/c/d/isis-jihad.jpg is blocked*, *"Tor
potentially unreachable"* is more valuable than *"Tor directory authority boo"*,
*"Only gambling seems to be blocked"* is more interesting than unreadable lists
of 100500 online casinos, etc.

Test name is useful for techies, but `http_request` does not differ from `web_connectivity` for the purpose of *general website reachability study*.

Most of measurements are normal, showing them by default puts mental burden on researcher. There may be false negatives like [unknown blockpage](https://explorer.ooni.torproject.org/measurement/20161114T223608Z_AS4788_eniUZ3PFBDLMpdUzLV02rrcEfzCr8HECuDa2kWCGp09MW7Gi6w?input=http:%2F%2Fwww.royalvegas.com) or [Turkish](https://twitter.com/atoker/status/794556207625338881) [throttling](https://explorer.ooni.torproject.org/measurement/20161103T235715Z_AS9121_8ZtHnB1W0a3IlAzPOq2m2CQKvMzx1k7p5XGIGOJQ7Kl201oMsP?input=https:%2F%2Fweb.whatsapp.com%2F), but *interesting* measurements MUST stand out.

Moreover, we're throwing out the data on FN/FP (False Negatives, False Positives) markup that is produced during country-specific research. We should store this data to verify that our pipeline has no regressions as soon as we get some input from blood-and-meat-based classifier on some datapoint (measurement).

There should be four color codes instead of two:
- Green — everything is OK, nothing interesting here
- Yellow — known "false positives": Cloudflare captcha, Cloudflare region-based *Access denied*, User-Agent based *Access denied* (e.g. `fepproject.org` denies curl). What else? Webserver error pages matching website webserver?
- Orange — non-explicit network anomaly including IP blackhole, throttling, known webserver error pages. Orange may change color on deeper investigation.
- Red — confirmed "censorship": known blockpage, redirect to unrelated address, **injected** TCP-Reset with clear evidence of injection, reachable dead website, etc.
Also, DDoSed website goes offline for everyone, but that's still a form of censorship. We don't measure it, but we probably should not paint unreachable website that is known to be alive with Green.

Possible tiny UI improvements:
- Measurement page: permalink for measurement data pages to cite them
- Measurement page: *[Flag] Countryname* may be a link to a country instead of *Back to Country* being lost on the other side of the webpage
- Measurement page: expand the 1st layer of `Object`. Exposing `Object` is ugly, but making it hard-to-find is even worse.
- Country page: *Blocked Websites* may be ranked according to, for example, Alexa. It's way better than plain A-to-Z as it provides more context. Website thematics may be shown (also, *Facebook* may be a separate theme instead of general *Social media*).
- Country page: American date format like *MM/DD/YY* looks so weird...
- Country page [barchar](https://explorer.ooni.torproject.org/country/TR#blockpageCount-bar-chart): 1) cursor is a hand on hover, but click does nothing; 2) repeated dates on x-axis; 3) date gaps & saw-shaped chart even for "stable" flow of measurements

