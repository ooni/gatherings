# OONI Mobile

In this session we brainstormed about the next steps for the OONI mobile
client.

## Session notes

* Add uninstall instructions to website with tips on how to remove traces of
  ooniprobe mobile.

* Register an account for Open Observatory on Apple Store and Google Play

    - Alternative use [The Tor Project](https://play.google.com/store/apps/developer?id=The+Tor+Project) account for publishing apps, it shares some "power of brand", but it induces another latency to release (signing), but stores has their own latencies so it may be not a big deal. Moreover, we don't know yet if TPO is OK with that.

* We should publish to alternative stores as well (F-Droid?) as Google Play may be blocked.

* There is collaboration idea for OONI and OrBot shared by n8fr8@ — passive detection of censored apps and websites & automatic redirection of blocked websites to Tor connection. It gives better latency to OrBot user who does not care about anonymity, but cares about network interference. It gives lots of data to OONI regarding website censorship.

* Check if there is anything valuable in `struct tcp_info`, as it can be polled by `getsockopt(TCP_INFO)` without root privileges, it may provide some useful metadata in pcap-free non-rooted [Android environment](https://code.google.com/p/android/issues/detail?id=38881).

* It's possible to probe TFO (TCP FastOpen) against known endpoints to detect middleboxes.

* Mobile client may be roaming between Wi-Fi networks or Wi-Fi/3G. Every time the network is changed new report should be recorded as ISP may be changes as well. Should the client mitigate it or is it server-side responsibility?
