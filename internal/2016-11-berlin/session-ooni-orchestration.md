# OONI Orchestration System

The OONI orchestration system is designed to instrument probes on what they
should be doing in terms of what they should be testing, how and at which
frequency.

## Session notes

We began with saying that it would be useful to have a smarter system for
orchestrating probes, but we had to first scope out what exactly it is that we
should be orchestrating.

The three broad parameters that could be orchestrated are:

* Frequency (how often do you do a certain test?)

* Target (what endpoint are you testing?)

* Test (what test should be run)

For the initial version we mostly care about being able to orchestrate
frequency and the target for predefined test.
It's currently out of scope to be able to also send new tests to probes via
orchestration.

It's important to have some sort of accounting on what are the tests that the
OONI team decides should be triggerred on probes.

There are also concerns about whether users that are participating to
orchestration have a higher risk than those not using ooniprobe via
orchestration.

One of the design goals of orchestration is that by making tests more tailored
for a specific user, we can potentially avoid consuming too much bandwidth by
employing smarter scheduling.

It should also be possible for a user to set a quota of the maximum number of
tests run per day.

Telemetry abou the device should also be collected to better inform scheduling
(how much battery does the device have? is it on a wifi or mobile network,
etc.)
