# IP Blocking vs Throttling

It's very hard to distinguish when targetted throttling and IP blocking and
distinguish it from transient network failures.

During this session we discussed some approached to go abouts doing that.

## Session notes

* Turkey is not only throttler, Iran and Venezuela seems to do it as well.

* Using NDT as a baseline to measure *targeted* throttling, NDT bandwidth measurements (bandwidth *available*) may be compared to bandwidth *consumption* during website loading

* Historical measurement for the specific website is another baseline as non-targeted throttling is network anomaly too

* Using phantomJS or another browser engine (shipped with ooniprobe) to check throttling or damage caused by blockage of cdn.social.net. The browser is also useful to check collateral damage caused by IP-based CDN blockages.

* Dropping random packets

* Running traceroute on top of TCP sessions

* Possible userinfo leak in traceroute — 2nd hop router pinpoints user more precisely than bare AS number.

* Bufferbloat can be measured with uTP

* Running a set of base tests as part of web connectivity

* IP info metadata used by ICLab: `ip.id`, `ip.ttl`, `tcp.flags.reset`. TCP options set, order, timestamps, window sizes, RTT, list of open ports & ICMP responses are **not** used, so that's sort of newish metadata to gather.

* Storing PCAPs locally on users devices and using orchestration to trigger
  sandboxed processing of them to avoid publishing of the pcap (and possibly leaking the data).

* Maybe better to use tcpdump rather than custom network code.
