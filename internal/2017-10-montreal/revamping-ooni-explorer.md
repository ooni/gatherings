# Revamping OONI Explorer

The current OONI Explorer is based on the old version of the data processing pipeline. Also this was a project that was developed quickly, within a few months.

## Why do users use OONI Explorer?

* Know what censorship is happening in a country or around the world

## Who are the users/personas of OONI Explorer?

* Journalist/Activist/Lawyer

* Technical exper/researcher

* OONI Probe user

## View

* Basic mode

* Advanced mode

Creation of a Dashboard, which provides country views. This will include a search which will be more of a power user thing.

And then you have the details view ==> which shows you the details of measurements.

What you expose also depends on the mobile app revamping.

Search --- based on URLs, ASNs, etc.

Let's walk people through what the data is saying. Rather than annotating the data itself, we could do more interpretation of the log. 

We should not require users to explore measurements based on test names (e.g. Web Connectivity). -- Improve/change labeling of things.

The basic view should have a sum of all types of censorship, not only web censorship. It would be best to have an aggregate view.

Include information on how to circumvent censorship in a country (e.g. use Tor with this pluggable transport).

The new Dashboard can include the following types of information in the home page:

1. Blocked websites (Expose blocked sites and potentially anomalous measurements as well)

2. Circumvention tools (Vanilla Tor, Bridge Reachability, etc.)

3. Speed and performance (NDR and DASH)

4. Middleboxes

5. Instant Messaging Apps (WhatsApp, Facebook Messenger, Telegram)

6. Censorship techniques



Open tickets:

1. CSV files

2. Other small fixes before the full revamping 

