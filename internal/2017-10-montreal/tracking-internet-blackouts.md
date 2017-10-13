# Tracking Internet Blackouts

We have a lot of questions and hypotheses, but we are better off rolling out an experiment.

Eventually we would like to roll out a methdology as part of the OONI Probe mobile apps.

On a mobile phone you have many more things that you can't rely on on a computer, which is why we will focus on mobile based methodology. We might also adapt it to dekstop later on.

We will set up a test lab in Kashmir --- we have a volunteer for this. He will receive hardware. 3g dongles, etc and set it up in Kashmir. 

We will have root on this thing and we will be able to roll out experiments.

We'll be using push notifications and we will have some kind of ping notification which will be initaited by us over probe orchestration. All this does is some background process and it expects to receive another one within a time interval and if it doesn't, then it enters some "OMG" state. Then it will start gathering data that can help us evaluate what is wrong.

What if it's connected to a network but it doesn't have data roaming enabled? What if it's in airplane mode? These things though can generally be detected from the mobile phone itself. 

What we're actually looking for is a situation where the probe was previously on a network (because it received a push notification) and then at some point it was expecting to receive another push notification, it hasn't, and yet it can't connect. 

We need to take these things into account when we roll this out. 

We should also send alerts to the user asking what's happening. 

We want to do a contextual pop-up in the edge cases --- to collect further evidence of blackouts.

## Scenarios that look like internet blackouts but ARENT (and how do we detect the differences) / possible false positives:

1. Changing location and going somewhere without much internet access ---- how to capture geolocation in a privacy-preserving way? We should also record the speed!

2. Airplane mode

3. Out of data

4. International roaming may not be working

## Actions

1. Pop-up telling users to run tests

2. Manually initiated tests

3. Scan for GSM networks (get neighbouring info)

4. Ask users for a screenshot

5. Ask users some questions -- things to do in the physical world (create a checklist of things they should be doing/checking)

6. Scan wifi networks to see if there was an increase or a drop (it can tell you whether the power went off) -- we probably want to keep a permanent cache of the state of wifi networks (to see when they go on and off)?

7. Ask them to call some phone numbers to check if they work (we could potentially set up some numbers)

8. Ask the to dial their telco (scrape those numbers from WhoIs records)

hologram.io --> for getting a SIM that roams with most data, pay as you go (as last resort back-up).
