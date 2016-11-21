# IP Blocking vs Throttling

It's very hard to distinguish when targetted throttling and IP blocking and
distinguish it from transient network failures.

During this session we discussed some approached to go abouts doing that.

## Session notes

* Using NDT as a baseline

* Using phantomJS in testing

* Dropping random packets

* Running traceroute on top of TCP sessions

* Bufferbloat can be measured with uTP

* Running a set of base tests as part of web connectivity

* Storing PCAPs locally on users devices and using orchestration to trigger
  processing of them.

* Maybe better to use tcpdump rather than custom network code.
