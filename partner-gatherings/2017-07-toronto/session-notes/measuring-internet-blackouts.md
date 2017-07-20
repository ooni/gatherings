# Measuring Internet Blackouts

Shutdown: Complete unreachability of anything outside of your local network
(i.e. the internet).

Blackout monitoring falls into the the following categories:

From outside towards inside:
* YODA/CAIDA


Aggregate monitoring:
* Google/Wikipedia
* Mozilla Telemetry
* NDT (MLab)

Problems:
* They don't provide local information (not fine grained enough)
* They do not apply to the mobile network

BGP data:
* BGP Announcement Data

Problems:
* In some cases there can be a blackout, but there will be no BGP Widthdrawal
* It may not be localised enough to tell which regions it's affecting

Raised the point of what you do when you have this data.

Take action and make a case for standing up against blackouts.

What is the best case scenario? If we could have any data, what data would we
need in order to make the strongest possible claim?

## Next Steps:

* Develop methodology in ooniprobe
* How to geolocate in a privacy preserving way?
* How do we collect data we need in a way that we are bandwidth preserving?
* Convince more organisations to publish data and be granular enough to pinpoint a shutdown.
