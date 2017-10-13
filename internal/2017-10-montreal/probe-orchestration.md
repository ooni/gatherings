# Probe orchestration

The vision is to be able to have unattended, automatic, instrumented tests.

The only thing blocking on this front: How do we do this in a secure way? How do we secure our infrastructure?

Probe orchestration roster: All orchestration requests are going to be signed with a hardware security module. When you create a request, you need to copy paste a command that spits out the orchestration request. You copy paste that into the web UI, and this is something that we send to clients.

The hardcoded keys are in the app, that can check the validity of an orchestration request.

Rather than adding the complexity of certificate authorities, we push update of app and this allows us to add new people to the keys and handle revocation and updating of keys.

From the app point of view ---> You have a task endpoint that you pass it an ID (through push notification), and you get back a json blob that is signed. This is another design choice to aid simplicity. We want to schedule specific subsets of URLs, but we want to be able to change this dynamically. And we don't want to have to sign all the individual subsets manually. So you have a signed blob, and an unsigned sub-part. 

We're going to be using JWT and you have a section like an expiry date, so we will set reasonable expiry dates. 

If you have already accepted an ID, the app will record that so that you don't run it again. 

We should display what is being orchestrated through a web interface.

Users are not by default opted-in to probe orchestration. To incentivise people to opt-in to probe orchestration, we need to think about UI and design, and ask our partners to opt-in.

Probe orchestration will get reviewed by OTF security people.

There are some fairly important tasks:

* Pagination for clients (the client view in the web UI takes 60 seconds, currently)

* Experimental branch for adding accounts

Any help on the above is greatly appreciated.
