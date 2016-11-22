# OONI Orchestration System

The OONI orchestration system is designed to instrument probes on what they
should be doing in terms of what they should be testing, how and at which
frequency.

## Session notes

We began with saying that it would be useful to have a smarter system for
orchestrating probes, but we had to first scope out what exactly it is that we
should be orchestrating.

The three broad parameters that could be orchestrated are:

* Frequency (how often do you do a certain action: test, fetch target-list, check updates?)

* Target (what endpoint are you testing?)

* Test (what test should be run)

For the initial version we mostly care about being able to orchestrate
frequency of tests and the target for predefined test.

Probe orchestration is not "public for everyone", only trusted entities can add
tests as it should not be trivial to enumerate ALL probes using rich
orchestration API:

1. Add https://malicious.ws/pingback URL to list via "public" orchestration API
2. …
3. PROFIT!

There are at least four different "rings" of orchestration API completeness & scariness:

0. RING-0 — push the code to the ooniprobe to execute (new test methods, etc.)
1. RING-1 — push testlist to the ooniprobe (new URLs)
2. RING-2 — push schedule adjustments for anything (test-lists, up-to-date checks, scheduling existing but not-enabled test methods against known test lists like `tls_handshake`, etc)
3. RING-3 — push schedule adjustments only for the measurements that are already scheduled because of existing code, test list and decks enabled by user

RING-3 is still useful as it provides weak incident response for short incidents (lasting less than 24 hours) and centralised dynamic workload scheduling.

It's currently out of scope to be able to also send new tests to probes via
orchestration (RING-0).  Also it's hard to push new code to iPhone, even if this code is
a bytecode / symbolic code for some in-app VM (e.g. LUA). Alike behavior is
prohibited by Appstore rules.

It's important to have some sort of accounting on what are the tests that the
OONI team decides should be triggered on probes.

There are also concerns about whether users that are participating to
orchestration have a higher risk than those not using ooniprobe via
orchestration.

One of the design goals of orchestration is that by making tests more tailored
for a specific user, we can potentially avoid consuming too much bandwidth by
employing smarter scheduling.

It should also be possible for a user to set a quota of the maximum number of
tests run and/or bandwidth consumed per day.

Telemetry about the device may also be collected to better inform scheduling
(how much battery does the device have? is it on a wifi or mobile network,
etc.)

Target orchestration latency is ~1 minute. Also, PUSHes on mobile platforms may have worse latency.
