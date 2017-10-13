# Censorship Alert System

## Where to push alerts?

* Emails

* Push notifications to apps (through subscription, perhaps)

* Orchestration

## What is the message?

* New website is blocked

* New filtering method deployed

* Censorship leak between countries

* New blockpage

There are lots of different messages that can be the outcome of the Censorship Alert System (CAS).

The messages need to be targeted --- via subscription, through which users can choose what they are interested in.

We can have an archive of everything sent out, but we can send out targeted messages to people depending on what interests them.

The Censorship Alert System will list events daily to a public mailing list.

Users need filters -- UN a few days later, US state department same day.

## How can we distinguish the urgent stuff from the non-urgent stuff?

* Flag new blocks

* Flag new things unblocked

* Flag new categories (of sites) blocked

* We can flag things in volume (e.g. when many services get blocked)

Depending on the feed, based on that we can determine what is more urgent and what is not.

Censorship events will be flagged once there is a change in what is being blocked in a country.

Create a web interface to show the incoming alerts --- and based on those determine what will be sent out as an alert (based on urgency).

In the pipeline, we will add another task to the DAG, which will be responsible for flagging censorship events.

The flagged events feed will be accessible through the web view (which could be superset, searchable and for queries).

What are censorship events?

1. IM app got blocked in your network in your country

2. Tor got blocked in your network in your country

3. Other circumvention tools got blocked in your country

4. Middleboxes got fingerprinted in your network (e.g. we detected squid)

5. oracle.com is now blocking users in your region

6. The first news site in your country got blocked

7. Throttling is now taking place in your network/country

8. Censorship techniques in your country now changed

9. There seems to be much less blocking in your country than normal

(We did not reach consensus on whether a censorship event includes also the network inside the country.)

Create tickets for the above.
